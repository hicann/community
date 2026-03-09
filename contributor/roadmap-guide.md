# 使用Gitcode Issue发布和管理Roadmap

## 概述

CANN社区推荐使用Gitcode Issue对各开发组织的规划和中长期目标进行追踪和管理。本文档对CANN社区各项目编写Roadmap类Issue给出参考和规范，以帮助各开发团队制定和维护高质量的Roadmap。

---

## 完整示例

以下是一个完整的Roadmap Issue示例，展示了所有推荐元素的实际应用。建议先浏览此示例以获得整体印象，再阅读后续的详细规范说明。

```markdown
# Ops-nn Development Roadmap (2026 Q1)

Ops-nn是CANN社区的核心算子库，本季度重点聚焦于算子覆盖率提升和性能优化。欢迎社区开发者参与贡献和反馈！

## Focus

• New feature & function: 新增50+高频算子支持
• Feature compatibility & reliability: 完善算子精度测试和边界条件处理
• Usability: 优化算子API设计，降低使用门槛
• Kernel optimization: 重点算子性能提升20%以上
• Documentation: 完善算子开发指南和API文档

## Base Operators

• 新增Transformer类算子支持
  - Goal: 支持MultiHeadAttention、LayerNorm等10个Transformer核心算子
  - Owner: [@zhangsan](https://gitcode.com/zhangsan)
  - Issue: [Transformer算子支持计划 #156](https://gitcode.com/cann/ops-nn/issues/156)

• FlashAttention算子实现 [🙋 Help Wanted]
  - Goal: 实现高效的FlashAttention算子，支持长序列推理场景
  - Owner: TBD
  - Issue: [FlashAttention实现 #178](https://gitcode.com/cann/ops-nn/issues/178)

## Performance Optimization

• MatMul算子性能优化
  - Goal: 大shape场景下性能提升30%
  - Owner: [@lisi](https://gitcode.com/lisi)
  - Issue: [MatMul性能优化 #189](https://gitcode.com/cann/ops-nn/issues/189)
  - PR: [MatMul kernel优化实现 #201](https://gitcode.com/cann/ops-nn/pulls/201)

• 算子融合框架
  ◦ 支持Conv+BN+ReLU融合
  ◦ 支持MatMul+Add融合
  ◦ 提供自定义融合规则接口
  - Goal: 减少30%的kernel launch开销
  - Owner: [@wangwu](https://gitcode.com/wangwu)

## Testing & Quality

• 算子精度测试框架完善 [🙋 Help Wanted]
  - Goal: 覆盖所有算子的精度基线测试
  - Owner: TBD
  - Issue: [精度测试框架 #145](https://gitcode.com/cann/ops-nn/issues/145)

## Sub-issues

### 历史 Roadmap

[Ops-nn Development Roadmap (2025 Q4) #120](https://gitcode.com/cann/ops-nn/issues/120)

### 特性子 Issue

[FlashAttention详细设计 #180](https://gitcode.com/cann/ops-nn/issues/180)
```

---

## 核心结构

### 1. 标题格式

**格式：** `[项目] Development Roadmap (时间周期)`

**示例：**
- `Ops-nn Development Roadmap (2026 Q1)`
- `catlass Development Roadmap (2025 Q4)`

**特点：**
- 清晰标示时间周期（季度为主）
- 便于版本管理和历史追踪

---

## 内容组织结构

### 2. 顶层内容

#### 2.1 开场描述（可选）

提供项目概述、愿景或总体方向简述。

#### 2.2 Focus/重点聚焦部分

通过**bullet points**（•）列出本周期最关键的3-5个聚焦方向，建议按照项目的**功能领域**或**技术模块**进行分组，涵盖全局视角：

```markdown
## Focus

• New feature & function: 新增50+高频算子支持
• Feature compatibility & reliability: 完善算子精度测试和边界条件处理
• Usability: 优化算子API设计，降低使用门槛
• Kernel optimization: 重点算子性能提升20%以上
• Documentation: 完善算子开发指南和API文档
```

**特点：**
- 概括和整体性描述当前周期当前项目的主要发展方向，不需要详细展开

---

### 3. 主要功能模块章节

#### 3.1 章节划分原则

按照项目的**功能领域**或**技术模块**进行分组，如完整示例中的：

- **Base Operators** - 基础算子
- **Performance Optimization** - 性能优化
- **Testing & Quality** - 测试与质量

#### 3.2 每个模块的结构

每个模块下包含多个**具体工作项**。根据工作项进展，有以下两种常见场景：

**场景1：仅有 Issue（规划/讨论阶段）**
```markdown
## Base Operators

• 新增Transformer类算子支持
  - Goal: 支持MultiHeadAttention、LayerNorm等10个Transformer核心算子
  - Owner: [@zhangsan](https://gitcode.com/zhangsan)
  - Issue: [Transformer算子支持计划 #156](https://gitcode.com/cann/ops-nn/issues/156)
```

**场景2：同时有 Issue 和 PR（实现阶段）**
```markdown
## Performance Optimization

• MatMul算子性能优化
  - Goal: 大shape场景下性能提升30%
  - Owner: [@lisi](https://gitcode.com/lisi)
  - Issue: [MatMul性能优化 #189](https://gitcode.com/cann/ops-nn/issues/189)
  - PR: [MatMul kernel优化实现 #201](https://gitcode.com/cann/ops-nn/pulls/201)
```

---

## 工作项信息字段

### 4. 关键元数据字段

每个工作项应包含的关键信息：

#### 4.1 Goal/Description
- **含义**：工作目标或简短描述
- **用途**：说明该工作项的目标
- **例子**：`Goal: 支持在代码仓配置流水线`

#### 4.2 Owner
- **含义**：责任人
- **格式**：`Owner: [@username](gitcode-profile-url)`
- **用途**：明确谁负责或主导该工作项
- **例子**：`Owner: [@zhangsan](https://gitcode.com/zhangsan)`

#### 4.3 Issue
- **含义**：关联的Gitcode Issue
- **格式**：`Issue: [标题 #编号](链接)`
- **用途**：追踪详细设计和讨论
- **例子**：`Issue: [机器人检视意见优化 #42](https://gitcode.com/cann/infrastructure/issues/42)`

#### 4.4 PR（Pull Request）
- **含义**：相关的实现PR
- **格式**：`PR: [标题 #编号](链接)`
- **用途**：链接实现工作
- **例子**：`PR: [新增CI指导及FAQ文档 #35](https://gitcode.com/cann/infrastructure/pulls/35)`

---

## 结构化方式

### 5. 多层级内容组织

#### 5.1 主工作项
顶层的核心工作项：
```markdown
• 优化各仓库CI端到端时间，达成30min内完成CI
```

#### 5.2 子工作项/相关项
使用**◦** 表示从属项目：
```markdown
• 主工作项
  ◦ 支持在代码仓配置流水线
  ◦ 数字化看板，实时监控资源利用率情况
  ◦ 相关项目 3
```

#### 5.3 链接信息
每个工作项下方缩进列出相关链接：
```markdown
- Owner: [@name](link)
- Issue: [#123](link)
- PR: [#456](link)
```

---

## 最佳实践

### 6. 编写建议

#### 6.1 清晰度
- 每个工作项应该清楚可理解
- 避免过于宽泛或含糊的描述
- 使用具体的技术术语

#### 6.2 可追踪性
- 为每个工作项关联Issue
- 标明负责人（Owner）

#### 6.3 完整性
- 覆盖所有主要功能领域
- 包含基础设施和维护工作
- 考虑跨功能协作

#### 6.4 可操作性
- 工作项应该足够具体可执行
- 提供目标和优先级指示
- 链接实现相关资源

#### 6.5 开发者协作
- 明确表述需要征集社区开发者反馈和贡献的工作项
- 提供定期讨论的渠道和时间（如会议周期和链接等）

#### 6.6 🙋 Help Wanted 标记

对于希望社区开发者重点参与贡献的工作项，建议使用 **[🙋 Help Wanted]** 标记进行标识：

```markdown
## Base Operators

• FlashAttention算子实现 [🙋 Help Wanted]
  - Goal: 实现高效的FlashAttention算子，支持长序列推理场景
  - Owner: TBD
  - Issue: [FlashAttention实现 #178](https://gitcode.com/cann/ops-nn/issues/178)
```

这一实践参考自其他开源社区的做法，有助于：
- 明确标识哪些工作项需要更多社区贡献者参与
- 降低新贡献者的参与门槛
- 提高项目的社区活跃度

---

## 补充元素

### 7. 可选补充内容

#### 7.1 Sub-issues
在Roadmap Issue底部列出跨周期关联的Roadmap Issue或大型工作项的拆分Issue。

**与工作项Issue字段的区别：**
- **工作项中的Issue字段**：链接的是具体工作项的详细设计、讨论或跟踪Issue
- **Sub-issues章节**：用于关联其他周期的Roadmap Issue（如上一季度未完成的工作），或将大型工作项拆分为多个独立追踪的子Issue

```markdown
## Sub-issues

[Ops-nn Development Roadmap (2025 Q4) #12780](link)  <!-- 关联上季度Roadmap -->
[Feature X Phase 2 #12800](link)                     <!-- 大型工作项的拆分 -->
```

#### 7.2 Assignees
在Issue属性中设置多个负责人，便于追踪。

#### 7.3 时间线修订
- 通过编辑活动历史记录时间周期变化
- 保持Issue title与实际时间周期同步

---

## 简化版模板

如果团队刚开始使用Roadmap Issue，可以从以下简化版本开始：

```markdown
# [项目名] Development Roadmap (20XX QX)

欢迎社区开发者参与贡献和反馈！

## Focus

• [重点方向1]: [简要描述]
• [重点方向2]: [简要描述]
• [重点方向3]: [简要描述]

## [功能模块1]

• [工作项1]
  - Goal: [目标描述]
  - Owner: [@username](profile-link)
  - Issue: [#123](issue-link)

• [工作项2] [🙋 Help Wanted]
  - Goal: [目标描述]
  - Owner: TBD

## [功能模块2]

• [工作项1]
  - Goal: [目标描述]
  - Owner: [@username](profile-link)
```

---

## 关键特点总结

| 特性 | 说明 |
|------|------|
| **时间粒度** | 按季度划分（Q1-Q4）或半年度 |
| **结构化** | 按功能模块组织，便于浏览和查询 |
| **可追踪** | 每项都关联Issue、PR和讨论链接 |
| **渐进式** | 支持多层级（主工作项→子工作项） |
| **灵活性** | 支持编辑和更新，反映实际进度 |
| **协作性** | 通过🙋标记征集社区贡献 |
| **清晰度** | 明确目标和负责人，便于责任分配 |
