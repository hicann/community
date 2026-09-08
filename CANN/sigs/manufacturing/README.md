# Manufacturing SIG

## 概述

Manufacturing SIG（简称：MFG SIG）是 CANN 社区面向制造业垂直领域的特别兴趣小组，覆盖工业软件、工业视觉等核心场景，聚焦制造业领域常用的三维视觉算法和智能制造解决方案领域的计算需求。

本 SIG 面向工业软件开发者、智能制造算法工程师、三维视觉与几何深度学习研究者、CANN 算子开发与部署开发者，以及高校实验室和制造业企业，围绕昇腾平台建设开放易用、可复现、可迁移的制造业 AI 应用生态。沉淀业界主流工业软件和工业视觉模型在昇腾平台上的算子库与训推样例。

## 愿景与使命

### 愿景

面向制造业真实工业场景，建设开放易用、可复现、可迁移的 CANN 行业算子库。

### 使命

使能开发者基于 CANN 完成工业软件与工业视觉领域的算子开发、模型训推、部署验证和 Benchmark 共建，降低制造业 AI 模型从 CUDA 等生态迁移至昇腾平台的成本。

## 工作目标

- 补齐 CANN 生态在工业软件三维识别与工业视觉场景的算子缺失，补齐三维稀疏计算的 NPU 能力；
- 推动业界主流工业软件与工业视觉模型在昇腾平台上完成算子适配、训练、推理和部署，沉淀可复现的样例与中文文档；
- 建立覆盖参数域采样与修剪、B-rep 拓扑构建、拓扑卷积与编码、结构注意力与预训练、滤波与降采样、配准与特征聚类、稀疏卷积、位姿特征与投票等 8 类算子的技术体系；
- 通过性能优化与多框架兼容，降低制造业用户使用门槛，落地典型行业场景；
- 维护 SIG 相关仓库、Issue、Pull Request、技术文档和社区协作流程；
- 联合高校、科研机构、制造业企业和社区开发者，共同推进昇腾制造业 AI 生态建设。

## 职责与范围

Manufacturing SIG 建设两个核心仓库，覆盖工业软件和工业视觉两大方向。

### 核心仓库

| 仓库 | 职责范围 |
| --- | --- |
| [mfg-ops-cax](https://gitcode.com/cann/mfg-ops-cax) | CAD 特征提取网络训推、B-rep 拓扑构建与理解、参数域采样与修剪、拓扑卷积与编码、结构注意力与预训练 |
| [mfg-ops-vision](https://gitcode.com/cann/mfg-ops-vision) | 三维目标检测、6DoF 姿态估计、滤波与降采样、配准与特征聚类、稀疏卷积、点云编码与分割聚类 |

## 协作边界

- 本 SIG 聚焦制造业领域的技术路线、算子适配与开发、模型训推、评测规范和真实工业场景验证；
- 基础算子、驱动、编译、运行时及基础系统能力依托 CANN 社区现有项目和相关 SIG；
- 本 SIG 是对现有算子 SIG 组在行业垂直领域的扩展和补充，为制造业行业提供开箱即用的 AI 工具链。

## 成员

### Maintainer 列表

- 庄瑞炎 [@laozhuang7271](https://gitcode.com/laozhuang7271), *15617240@qq.com*
- 曹杰文 [@debrencc](https://gitcode.com/debrencc), *caojiewen@huawei.com*
- 程黎明 [@huatee](https://gitcode.com/huatee), *chengliming@huawei.com*

### Committer 列表

- 李梓和 [@lizihe11](https://gitcode.com/lizihe11), *lizihe@ncti-gba.cn*
- 伍宇明 [@engineer566](https://gitcode.com/engineer566), *ferriswym@163.com*
- 文君逸 [@junyi-wen](https://gitcode.com/junyi-wen), *meng-duo@qq.com*
- 刘心唯 [@sumwailiu](https://gitcode.com/sumwailiu), *798465811@qq.com*
- 林洁 [@weixin_43555315](https://gitcode.com/weixin_43555315), *llinjie1024@163.com*
- 许永佳 [@Xu_Yongjia](https://gitcode.com/Xu_Yongjia), *2359865877@qq.com*
- 杨普旭 [@YANGPuxu](https://gitcode.com/YANGPuxu), *yingtao0427@gmail.com*

其他 Committer 将在完成 GitCode 账号注册、CLA 签署和角色确认后，按照 CANN 社区治理流程逐步补充。

## 社区运作

### 会议组织

- 公开会议频率：北京时间，月度例会，每月最后一周周五上午 10:00~11:00；
- [CANN 社区会议平台](https://meeting.osinfra.cn/cann/)
- 议题申报及会议纪要：会前一天截止申报议题，会后三天内归档会议纪要。

例会主要跟踪以下内容：

- SIG 仓库建设与技术路线；
- 算子开发、适配和合入进展；
- Issue 和 Pull Request 处理情况；
- Benchmark 和行业场景建设；
- 社区贡献者及成员增补；
- 与 CANN 社区其他 SIG 的协同事项。

### 邮件列表

- SIG 邮件列表：[manufacturing@cann.osinfra.cn](mailto:manufacturing@cann.osinfra.cn)

邮件列表用于发布会议通知、议程、会议纪要和 SIG 重要事项。

## 贡献指南

欢迎高校、科研机构、制造业企业和个人开发者参与 Manufacturing SIG 共建。

社区成员可以通过以下方式参与：

- 在相关仓库提交 Issue，反馈问题、需求或改进建议；
- 提交 Pull Request，贡献代码、文档、算子样例和测试用例；
- 参与 SIG 例会，讨论技术路线、接口规范和项目进展；
- 贡献工业软件与工业视觉领域的适配方案和实际案例；
- 参与昇腾平台上的算子迁移、性能分析和优化工作。

## 未来规划

### 基础攻坚阶段：2026 年 9 月—12 月

- 完成拓扑卷积等 10+ 核心算子的算子生成与单元测试；
- 搭建标准化工程架构；
- 完成 SIG 组织和治理信息配置；
- 建立仓库目录、文档和基础 CI 规范。

### 性能优化阶段：2027 年 1 月—3 月

- 聚焦稀疏计算性能优化与三维模型检索基础场景适配；
- 形成性能基准报告；
- 完成 20+ 核心算子开发。

### 场景落地阶段：2027 年 4 月—6 月

- 开发目标检测、姿态估计等智能制造算子组合模块；
- 落地端到端智能制造案例；
- 通过已有商业项目群带动，高校-开发企业-应用企业三方形成闭环落地。

### 生态深化阶段：2027 年 7 月—9 月

- 深化生态整合（对接 torch_npu、MindSpeed 等工具链）；
- 迭代高级功能，建立社区共建机制；
- 形成行业开源算子生态标杆。

一年期关键成果：2 个核心模型库（20+ 算子）+ 4 个典型案例发布。

## License

SIG 所属仓库采用 Apache License 2.0。所引用的上游模型、数据集及第三方组件遵循其各自许可证，并在对应仓库的 LICENSE 或 NOTICE 文件中进行说明。