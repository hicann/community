# CANNBot-Knowledge 仓开源测试报告

| 项目 | 内容 |
|---|---|
| 报告日期 | 2026-08-31 |
| 测试对象 | [`cann/cannbot-knowledge`](https://gitcode.com/cann/cannbot-knowledge) |
| 被测版本 | `0e144e64174a28d09477c713aa1f1fbf988076d9` |
| 测试范围 | API 知识检索；知识库接入 Flash 直调工作流的 CANNBench 线上对比评测 |
| 线上评测平台 | [CANNBench Official Tasks / Micro](https://cannbench.com/leaderboard/official-tasks/micro)，硬件 `950pr` |
| 总体结论 | API 检索和 Flash 直调工作流接入测试均**通过** |

## 1. API 检索能力测试

### 1.1 测试目标

通过知识库检索替换 CANNBot 基于 `ascendc-docs-search` Skill 逐文件翻目录的 API 查询方式，让 Agent 更高效地找到需要的 API 信息。

### 1.2 测试场景

#### 适用场景

- 开发 Ascend C 算子（如 `foreach_addcdiv_scalar`、`rms_norm`）时，需要确认 API 签名、参数含义或平台支持情况；
- 问题涉及具体开发硬件平台，如 910B、910B2 或 950；
- 需要同时查看 API 签名、参数、约束、示例和使用方法。

#### 不适用场景

- 需要查看官方文档原文或具体行号；
- 知识库索引不可用或对应 API 未收录。

### 1.3 前置条件与输入

- 知识库索引可用且已编译，使用 BM25F 倒排索引，覆盖 4,000+ 张知识卡；
- 已明确 API 名称和关键约束，如 `Div count 对齐`；
- 已明确目标平台标识，如 `a2`、`a3` 或 `950`；
- `knowledge-query` Skill 或 `knowledge_query.py` 可用。

### 1.4 检索步骤

1. **构造查询**：直接使用“实体 + 关键约束”，例如 `Div count 前n个元素`。不在 query 中添加“帮我看看参数签名”等填充词。
2. **执行检索**：指定 Ascend C 文档编译后目录和目标平台执行查询。

   ```bash
   knowledge_query.py search --query "<实体> <约束>" \
     --scope <asc-devkit编译后目录> --platform <平台>
   ```

3. **选择候选卡**：根据标题、摘要、路径和状态选择要阅读的卡片，优先选择平台匹配、状态为 `stable` 的卡片。
4. **打开卡片正文**：阅读 API 签名、参数含义、约束条件、示例和平台范围，不直接使用搜索摘要作答。
5. **核对来源**：确认来源确实支持准备采用的结论。多张卡片存在冲突时，先比较它们的平台、版本和来源。
6. **执行降级路径**：知识库未命中时，降级到 `ascendc-docs-search` 翻查官方文档原文。

### 1.5 预期产物

API 检索应生成带结论、适用范围、依据和限制的回答：

```text
结论：<API 签名和参数说明>
适用范围：<平台、版本和其他条件>
依据：<使用的知识卡和来源>
限制或冲突：<不适用情况或不同结论>
仍需验证：<源码、实验或性能分析>
```

### 1.6 对比实验设计

测试集包含 **75 条**真实 API 查询需求，均来自 CANNBot 实际算子开发过程。对同一批查询对比两种路径：

| 方案 | 说明 |
|---|---|
| Baseline | CANNBot 原生 `ascendc-docs-search` Skill，逐文件查找官方文档 |
| 知识库方案 | 本仓库提供的 `knowledge-query` Skill，通过知识索引查找 API 卡 |

每个查询单独开启一个会话，避免上下文干扰。实验分别使用 `deepseek-v4-flash`、`glm-5.2` 和 `minimax-m2.7` 三种模型，记录平均耗时、会话回合数、工具调用数和每条查询的 Token 用量。

### 1.7 测试结果

#### 第一轮：deepseek-v4-flash

| 指标 | docs-search（Baseline） | knowledge-query |
|---|---:|---:|
| 平均耗时 | 47.4s | **32.6s** |
| 回合数 | 7.8 | **6.3** |
| 工具调用 | 11.2 | **8.7** |
| Token/条 | 33.5K | **27.6K** |

#### 第二轮：glm-5.2

| 指标 | docs-search（Baseline） | knowledge-query |
|---|---:|---:|
| 平均耗时 | 58.3s | **44.9s** |
| 回合数 | 7.7 | **6.0** |
| 工具调用 | 11.2 | **8.1** |
| Token/条 | 33.3K | **26.8K** |

#### 第三轮：minimax-m2.7

| 指标 | docs-search（Baseline） | knowledge-query |
|---|---:|---:|
| 平均耗时 | 131.9s | **69.3s** |
| 回合数 | 9.2 | **5.8** |
| 工具调用 | 10.2 | **5.1** |
| Token/条 | 56.1K | **46.8K** |

上述结果用于比较两种 API 查询方式，不用于评价模型能力。不同轮次的绝对耗时会受测试时段和模型调用峰谷影响，应以同一轮次内的两种方案对比为准。

### 1.8 检索结果重合度

对同一批查询，两种方式查找结果的内容重合率 **>96%**。

不一致的主要原因是两套语料的组织粒度不同：同一 API 在官方文档中可能是独立文件，在知识库中则可能是经过知识编译后的聚合卡；也可能存在 reg 版和 memory 版归属不同的情况。整体上两种方式返回的是同一批正确文档，表明 `knowledge-query` 在提升效率的同时没有牺牲检索准确性。

### 1.9 实验结论

基于 75 条真实 API 查询需求的对比结果，`knowledge-query` 可以在保证检索质量不下降的前提下提升 API 查询效率：

- **速度更快**：三轮实验的端到端查询耗时均降低 15% 以上；
- **更省回合**：平均减少 1～2 轮交互，降低反复猜测文档路径的成本；
- **更少工具调用**：三轮实验中的工具调用数均有下降；
- **Token 消耗更低**：平均单条查询节省 5K 以上 Token；
- **检索质量保持稳定**：两种查询方式的结果内容重合率超过 96%。

综上，基于知识库的 API 检索方式满足效率与质量要求，本部分测试结论为**通过**。

## 2. 接入 Flash 直调工作流测试

### 2.1 测试目的

使用 CANNBench 线上成绩，对比接入 CANNBot-Knowledge 前后 Flash 直调工作流在指定 L1/L2 算子上的总得分，验证知识接入对工作流产出质量的提升效果。

### 2.2 测试对象与口径

| 角色 | CANNBench 方案标签 |
|---|---|
| 知识增强实验 | `CANNBot-Knowledge GLM-5.3` |
| 对照实验 | `direct-invoke@CANNBot GLM-5.3 OpenCode` |

对比条件：

| 项 | 说明 |
|---|---|
| Benchmark | `official-tasks` |
| Benchmark Version | `1.1.0` |
| Hardware | `950pr` |
| 统计口径 | 两个方案中相同的 8 个 L1/L2 算子 |
| 得分口径 | 汇总 8 个算子在公开评测集上的 `score` |

纳入统计的算子：

| 等级 | 算子 |
|---|---|
| L1 | `ForeachAddcdivScalar`、`SwiGlu` |
| L2 | `ApplyRotaryPosEmb`、`Cummin`、`Gather`、`RmsNorm`、`Scatter`、`Softmax` |

两个方案的全量覆盖算子数不同，因此不直接使用榜单的方案全量总分，而是对上述 8 个共同算子的得分重新汇总。

### 2.3 总分对比

| 方案 | 8 算子总分 | 相对对照提升 |
|---|---:|---:|
| `direct-invoke@CANNBot GLM-5.3 OpenCode` | 526.21 | — |
| `CANNBot-Knowledge GLM-5.3` | **610.14** | **+83.93（+15.95%）** |

计算方式：

```text
总分提升 = 610.14 - 526.21 = 83.93
总分提升比例 = 83.93 / 526.21 × 100% = 15.95%
```

### 2.4 结论

在 `official-tasks` 1.1.0、`950pr` 的相同评测条件下，接入 CANNBot-Knowledge 后，Flash 直调工作流在指定 8 个 L1/L2 算子上的汇总得分由 **526.21** 提升至 **610.14**，提升 **83.93 分（15.95%）**。

测试结果表明，CANNBot-Knowledge 对 Flash 直调工作流的算子产出质量具有明显提升作用，本部分测试结论为**通过**。

### 2.5 数据来源

- 榜单页面：[https://cannbench.com/leaderboard/official-tasks/micro](https://cannbench.com/leaderboard/official-tasks/micro)；
- 数据抓取时间：2026-08-31 11:39 CST；
- 方案数据通过 CANNBench 榜单 API 抓取，并按 `solution_tag` 精确匹配两组实验；
- 榜单成绩可随后续提交发生变化，本报告以上述抓取时点为准。
