# Financial Engineering SIG (FinEng)

## 概述

Financial Engineering SIG（简称：FinEng）是 CANN 社区面向金融工程垂直领域的特别兴趣小组，聚焦金融AI基础设施的智能化与算力精细化运营需求，覆盖金融时序预测与潮汐调度、大尺寸 MoE 部署推理、金融多模态训推三大核心场景。

本 SIG 面向银行、证券、保险等金融机构的 AI 开发者，金融大模型训练与推理工程师，CANN 模型训练与部署开发者，以及高校金融科技研究团队，围绕昇腾平台建设开箱即用的高性能 AI 训推工具链与领域算子库。

## 愿景与使命

### 愿景

面向金融工程真实业务场景，建设开放易用、可复现、可迁移的 CANN 应用生态，成为开源社区首个面向金融工程垂直领域的算子库。

### 使命

使能开发者基于 CANN 完成金融场景模型样例运行、策略训练与部署、真实业务验证和 Benchmark 共建，降低金融模型从 CUDA 等生态迁移至昇腾平台的成本。

## 工作目标

- 推动业界主流金融时序预测、MoE 大模型和多模态模型在昇腾平台上完成训练、推理和部署适配，沉淀可复现的样例与中文文档；
- 建设覆盖金融时序预测与潮汐调度、大尺寸 MoE 部署推理、金融多模态训推三大方向的技术体系；
- 建立统一的金融领域算子规范和评测协议，降低金融行业 AI 模型的跨场景复用成本；
- 通过真实金融业务场景开展功能和性能验证，并将发现的问题及需求反馈给 CANN 社区；
- 维护 SIG 相关仓库、Issue、Pull Request、技术文档和社区协作流程；
- 联合金融机构、高校、科研机构和社区开发者，共同推进昇腾金融 AI 生态建设。

## 职责与范围

Financial Engineering SIG 建设两个核心仓库：fin-ops-lib（算子仓）和 fin-recipes（模型仓）。

### 核心仓库

| 仓库 | 职责范围 |
| --- | --- |
| [fin-ops-lib](https://gitcode.com/cann/fin-ops-lib) | 频谱变换类、序列扫描类、量化与访存优化类、KV 缓存与投机采样类等算子 |
| [fin-recipes](https://gitcode.com/cann/fin-recipes) | 金融时序预测、潮汐调度、大尺寸MoE、多模态大模型等场景模型，训推优化实践 |

## 协作边界

- 本 SIG 聚焦金融工程领域的技术路线、模型适配、训练部署、算子开发、评测规范和真实业务验证；
- 底层算子、驱动、编译、运行时及基础系统能力依托 CANN 社区现有项目和相关 SIG；
- 本 SIG 与 CANN 社区现有 ops-nn / ops-math / ops-transformer 等通用算子库协同建设。FinEng SIG 侧重金融行业的垂直领域算子与模型；
- 通用模型优化、长上下文、AI Coding 等已有通用仓建设不在本 SIG 职责范围内。

## 成员

### Maintainer 列表

- 江瀚澄 [@gcw_MYVF23f8](https://gitcode.com/gcw_MYVF23f8), *jianghancheng_hf@163.com*
- 陈嘉远 [@danaodai2](https://gitcode.com/danaodai2), *chenjiayuan1077@163.com*
- 程黎明 [@huatee](https://gitcode.com/huatee), *chengliming@huawei.com*
- 付明亮 [@dongzihaotajiu](https://gitcode.com/dongzihaotajiu), *fumingliang1@huawei.com*

### Committer 列表

- 费秀宏 [@fay625](https://gitcode.com/fay625), *fay625@sina.cn*
- 洪文焕 [@HongEvan](https://gitcode.com/HongEvan), *hongwith@qq.com*
- 刘童 [@linjialq](https://gitcode.com/linjialq), *bjcrystal@126.com*
- 周家申 [@flysun55](https://gitcode.com/flysun55), *flysun55@163.com*
- 张兴 [@xingzhang8023](https://gitcode.com/xingzhang8023), *zhangxing8@huawei.com*


## 社区运作

### 会议组织

- 公开会议频率：北京时间，月度例会，每月第一周周五上午 10:00~11:00；
- [CANN 社区会议平台](https://meeting.osinfra.cn/cann/)
- 会议规范：会前一天截止申报议题，会后三天内归档会议纪要。

例会主要跟踪以下内容：

- SIG 仓库建设与技术路线；
- 算子开发、模型迁移、适配和合入进展；
- Issue 和 Pull Request 处理情况；
- 金融场景 Benchmark、数据格式和评测规范建设；
- 社区贡献者及成员增补；
- 与 CANN 社区其他 SIG 的协同事项。

### 邮件列表

- SIG 邮件列表：[fin-eng@cann.osinfra.cn](mailto:fin-eng@cann.osinfra.cn)

邮件列表用于发布会议通知、议程、会议纪要和 SIG 重要事项。

## 贡献指南

欢迎金融机构、高校、科研机构和个人开发者参与 Financial Engineering SIG 共建。

社区成员可以通过以下方式参与：

- 在相关仓库提交 Issue，反馈问题、需求或改进建议；
- 提交 Pull Request，贡献代码、文档、模型样例和测试用例；
- 参与 SIG 例会，讨论技术路线、算子规范、接口规范和项目进展；
- 贡献真实金融业务验证案例、数据格式、评测基准和业务适配方案；
- 参与昇腾平台上的金融模型迁移、性能分析和优化工作。

## 未来规划

### 第一阶段：基础攻坚（2026 年 9 月—12 月）

- 完成 3+ 算子基础实现与单元测试，搭建标准化工程架构；
- 完成 SIG 组织和治理信息配置；
- 完成两个仓库创建并推进初始化；
- 建立仓库目录、文档和基础 CI 规范。

### 第二阶段：性能优化（2027 年 1 月—3 月）

- 聚焦性能优化与金融基础场景适配；
- 落地金融时序预测与潮汐调度场景；
- 建立算子与模型的目录规范和文档模板。

### 第三阶段：场景落地（2027 年 4 月—6 月）

- 针对大尺寸 MoE 与多模态大模型训推场景，完成 3+ 行业算子开发与测试；
- 落地端到端行业案例；
- 发布金融领域 Benchmark 初版。

### 第四阶段：生态深化（2027 年 7 月—12 月）

- 深化生态整合与工具化，迭代高级功能；
- 加速模型迁移和优化效率；
- 建立社区共建机制；
- **一年期关键成果**：10个核心算子，5个行业模型库完成增训和部署，4个行业场景典型案例发布，形成行业开源算子生态标杆。

## License

SIG 所属仓库原则上采用 Apache License 2.0。所引用的上游模型、数据集及第三方组件遵循其各自许可证，并在对应仓库的 LICENSE 或 NOTICE 文件中进行说明。