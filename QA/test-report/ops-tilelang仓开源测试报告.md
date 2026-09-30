# ops-tilelang 仓测试报告

## 1. 概述

`ops-tilelang` 是面向 Ascend 平台、使用 TileLang DSL 实现的算子仓库，Python 包导入名为 `cann_ops_tilelang`。仓库声明支持 Ascend 950 架构，采用 Python 接口与 kernel 调度分离的组织方式，提供正确性测试、参考实现及性能回归工具。

本报告覆盖仓库中的 Attention、Compression、Engram、mHC、MoE、Multimodal、Normalization、Quant、Sampling、Tensor 十个业务域，以及公共工具和测试基础设施。根据代码快照静态统计，十个业务域共包含 **99 个公开导出 API 条目**、**53 个业务测试文件**，另有 **1 个公共工具测试文件**。导出条目包含辅助入口，不等同于独立 kernel 数；测试文件数不等同于参数化用例数。

### 1.1 特性范围

| 序号 | 业务域 | 导出 API 条目 | 主要测试内容 |
| --- | --- | ---: | --- |
| 1 | Attention | 20 | KV Cache 读写、索引转换、位置编码、状态缓存、推理解码元数据 |
| 2 | Compression | 2 | Prefill / Decode 压缩计算及状态更新 |
| 3 | Engram | 8 | 权重融合、Gate 前反向、梯度归并、Hash、Sinkhorn 相关计算 |
| 4 | mHC | 20 | Expand、Mix、GEMM、RMSNorm、Sinkhorn、Pre / Post 及前反向组合 |
| 5 | MoE | 3 | Top-k 路由、融合 Gate、权重归一化 |
| 6 | Multimodal | 5 | 图像位置、图像 Token 重排、Embedding 替换、图像转 Patch、相对位置计算 |
| 7 | Normalization | 2 | Norm / LayerNorm 接口及其参数组合 |
| 8 | Quant | 15 | 按 Token / Block / Channel 的类型转换与量化、Scale Factor、SwiGLU |
| 9 | Sampling | 19 | Softmax / LogSoftmax、随机与融合采样、LogProbs、掩码、推测解码辅助计算 |
| 10 | Tensor | 5 | Gather、Unbind、序列长度及索引处理 |


### 1.2 重点验证与问题处理范围

测试活动包括接口和功能验证、数值精度比对、边界与异常输入、AUTO / PTO 编译后端配套验证、性能回归、可靠性、安全与交付件检查。


## 2. 版本测试信息

**硬件和版本要求**

产品型号： Ascend 950PR&950DT

操作系统：覆盖以下测试因子组合

|      | 因子名称 | 因子取值               |
| ---- | -------- | ---------------------- |
| 1    | OS       | Euler/Ubuntu           |
| 2    | CPU架构  | ARM/x86                |
| 3    | 形态     | docker/标准host+device |

CANN版本：CANN 9.3.0(基于CANN weekly版本)

Python版本：Python >= 3.10

PyTorch：配套 torch 及 torch_npu 版本

cmake：>= 3.16

编译器：Bisheng（CANN工具链自带）


## 3. 测试结论

**测试结论：Pass。**

功能、精度、性能、可靠性、兼容性及安全测试结论均为通过。

单后端包含 **15,278 个用例**，AUTO 与 PTO 合计 **30,556 次后端用例执行**。

| 验收维度 | 验收要求 | 结论 |
| --- | --- | --- |
| 功能 | 发布范围内接口与算子行为满足定义，目标用例执行完整 | Pass |
| 精度 | 与对应参考实现比较满足各算子的数值容差和语义要求 | Pass |
| 性能 | 相同软硬件配套、相同形状与 dtype 下满足已确认的回归门限 | Pass |
| 可靠性 | 边界、重复执行及异常场景满足接口约定和稳定性要求 | Pass |
| 兼容性 | 目标硬件与指定 CANN / TileLang / PyTorch NPU 配套可用 | Pass |
| 安全 | 安全扫描、依赖检查和交付件检查满足项目出口要求 | Pass |
| 遗留问题 | 阻塞发布问题完成关闭或取得正式评审结论 | Pass |

## 4. 特性质量评估

| 序号 | 特性 | 测试结论 | 功能 | 精度 | 性能 | 可靠性 | 兼容性 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Attention 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 2 | Compression 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 3 | Engram 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 4 | mHC 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 5 | MoE 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 6 | Multimodal 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 7 | Normalization 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 8 | Quant 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 9 | Sampling 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |
| 10 | Tensor 算子族 | Pass | Pass | Pass | Pass | Pass | Pass |


## 5. DFX专项质量评估

### 5.1 安全测试

**安全测试结论：Pass。**

| 检查项 | 验收内容 | 结论 |
| --- | --- | --- |
| 静态代码检查 | 编码规范、危险调用及缺陷告警完成处理或评审 | Pass |
| 三方依赖检查 | 依赖版本、许可证及已知漏洞检查满足发布要求 | Pass |
| 输入安全与 Fuzz | 非法维度、dtype、索引等输入按接口契约处理；适用入口完成 Fuzz | Pass |
| 交付件安全 | 源码包 / Wheel 等实际交付件完成恶意代码及病毒扫描 | Pass |
| 配置与权限 | 运行权限、文件访问及环境配置符合最小必要要求 | Pass |


### 5.2 可靠性测试

**可靠性测试结论：Pass。**

| 序号 | 可靠性特性 | 测试结论 | 遗留风险处置要求 |
| --- | --- | --- | --- |
| 1 | 空输入、小规模与非对齐 Shape | Pass | 按各接口实际支持范围核验 |
| 2 | Tile / Block 边界、尾块与大词表 | Pass | 保留边界参数及输出比对记录 |
| 3 | 非法 dtype / shape / 参数 | Pass | 核对异常类型与接口约定 |
| 4 | 重复调用、输入保持与确定性 | Pass | 按是否原地修改及随机语义分别验收 |
| 5 | 显存与并发调度 | Pass | 补充显存峰值、长时间运行及并发压力记录 |
| 6 | 历史问题回归 | Pass | 保留原失败用例、修复提交和复测对应关系 |

### 5.3 性能测试

**性能测试结论：Pass。**

| 场景 | 模型 | 特性 | 性能指标 | 测试环境 | 测试结果 |
| --- | --- | --- | --- | --- | --- |
| 训练相关算子 | 算子级，未绑定整网 | Engram、mHC 前反向 | Kernel 耗时、有效带宽、显存峰值 | Ascend 950 配套环境 | Pass |
| 推理基础算子 | 算子级，未绑定整网 | Attention、MoE、Norm、Quant、Tensor、Compression | Kernel 耗时及回归幅度 | Ascend 950 配套环境 | Pass |
| 推理采样算子 | 算子级，未绑定整网 | Sampling 及大词表路径 | Kernel 耗时及回归幅度 | Ascend 950 配套环境 | Pass |
| 多模态算子 | 算子级，未绑定整网 | 图像 Token、Patch 与位置处理 | Kernel 耗时及显存峰值 | Ascend 950 配套环境 | Pass |

### 5.4 兼容性测试

**兼容性评估：Pass。**

| 序号 | 兼容性场景 | 验证结果 |
| --- | --- | --- |
| 1 | Ascend950 与指定软件栈 | Pass |
| 2 | AUTO / AscendC 编译后端 | Pass |
| 3 | PTO 编译后端 | Pass |
| 4 | Python 包导入、公共 API 与 Wheel 安装 | Pass |
| 5 | 接口命名调整后的仓内调用 | Pass |


## 6. 测试执行评估

### 6.1 测试覆盖

| 测试活动 | 测试结论 | 用例数 / 范围  | 用例通过率 |
| --- | --- | --- | --- |
| 特性测试 | Pass | 15,278 / 后端；最终数量待流水线核定 |100% |
| 性能测试 | Pass | 各业务域 benchmark；| 100% |
| 可靠性测试 | Pass | 边界、异常输入、重复执行与压力场景 | 100% |
| 继承特性测试 | Pass | 历史算子与缺陷回归；与特性测试存在交集 | 100% |
| 兼容性测试 | Pass | AUTO / PTO 与目标软硬件配套 | 100% |
| 安全测试 | Pass | 代码、依赖、Fuzz、交付件与配置检查 | 100% |

统计规则：

1. 同一 node ID 在不同后端分别计为一次后端用例执行；多轮复测不重复计入唯一用例总数。
2. 用例执行覆盖率 = 已执行目标用例数 / 目标清单用例数；用例通过率 = 通过数 / 已执行数，失败、错误、跳过需单独记录。
3. 业务域覆盖、测试文件覆盖和代码行 / 分支覆盖是不同指标。本报告不根据测试文件存在或执行结果推导代码覆盖率。
4. `OPS_TILELANG_TEST_LEVEL=0/1/2` 分别控制核心、默认和完整参数集合。当前 Nightly 配置显式使用 L0；“全仓路径”不等于“L2 全参数”。
5. 本表各类测试可能交叉覆盖，不将行间数量直接相加。

## 7. 遗留问题和关键风险

不涉及

### 7.1 遗留问题统计

不涉及

### 7.2 遗留问题列表

不涉及

## 8. 附件

不涉及
