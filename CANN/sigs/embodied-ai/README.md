# Embodied-AI SIG

## 概述

Embodied-AI SIG 是 CANN 社区面向具身智能领域的特别兴趣小组，覆盖机器人操作、运动控制、视觉语言导航、世界模型、3D 感知与重建等技术方向。

本 SIG 面向机器人操作、运动控制与导航开发者，VLA、世界模型及 3D 视觉研究者，CANN 模型训练与部署开发者，以及高校实验室和机器人企业，围绕昇腾平台建设开放易用、可复现、可迁移的具身智能应用生态。

本 SIG 主要沉淀业界主流具身智能模型在昇腾平台上的训练与推理样例，推动统一的数据格式、评测规范和硬件接口，并通过真实机器人进行功能与性能验证。底层算子、驱动及系统能力依托 CANN 社区现有项目和相关 SIG 共同建设。

## 愿景与使命

### 愿景

面向具身智能真实机器人场景，建设开放易用、可复现、可迁移的 CANN 应用生态。

### 使命

使能开发者基于 CANN 完成模型样例运行、策略训练与部署、真实硬件验证和 Benchmark 共建，降低具身智能模型从 CUDA 等生态迁移至昇腾平台的成本。

## 工作目标

- 推动业界主流具身智能模型在昇腾平台上完成训练、推理和部署适配，沉淀可复现的样例与中文文档；
- 建设覆盖机器人操作、运动控制、视觉语言导航、世界模型和 3D 感知等方向的技术体系；
- 建立统一的数据格式、评测协议和硬件接口规范，降低跨模型、跨本体和跨团队的复用成本；
- 通过真实机器人开展功能和性能验证，并将发现的问题及需求反馈给 CANN 社区；
- 维护 SIG 相关仓库、Issue、Pull Request、技术文档和社区协作流程；
- 联合高校、科研机构、机器人企业和社区开发者，共同推进昇腾具身智能生态建设。

## 职责与范围

Embodied-AI SIG 建设四个核心算法方向和四个公共使能方向。

### 核心算法方向

| 仓库 | 职责范围 |
| --- | --- |
| [embodied-manipulation](https://gitcode.com/cann/embodied-manipulation) | 机器人操作、VLA、模仿学习、强化学习以及夹爪和灵巧手策略 |
| [embodied-locomotion](https://gitcode.com/cann/embodied-locomotion) | 人形机器人、四足机器人全身控制和运动策略 |
| [embodied-navigation](https://gitcode.com/cann/embodied-navigation) | 视觉语言导航、SLAM、长程路径规划及自动驾驶 VLA |
| [embodied-world-model](https://gitcode.com/cann/embodied-world-model) | 生成式世界模型、NeRF、3D Gaussian Splatting、深度估计及点云重建 |

### 公共使能方向

| 仓库 | 职责范围 |
| --- | --- |
| [embodied-train](https://gitcode.com/cann/embodied-train) | 监督学习、模仿学习、强化学习、Sim2Real 和分布式训练样例 |
| [embodied-deploy](https://gitcode.com/cann/embodied-deploy) | 模型转换、ATC 编译、CANN 推理、融合算子调用及多硬件部署样例 |
| [embodied-benchmarks](https://gitcode.com/cann/embodied-benchmarks) | 操作、运动控制、导航和世界模型的评测基准、评测协议及数据格式 |
| [embodied-hardware-adapters](https://gitcode.com/cann/embodied-hardware-adapters) | Franka、ALOHA、Piper、Pika、宇树机器人及灵巧手等硬件的统一接口和 ROS 2 适配 |

上述八个仓库已完成创建，目前处于初始化、权限配置和首批内容筹备阶段。部分仓库在正式公开前可能仅对已授权成员可见。

## 协作边界

- 本 SIG 聚焦具身智能领域的技术路线、模型适配、训练部署、评测规范、硬件接口和真实机器人验证；
- 底层算子、驱动、编译、运行时及基础系统能力依托 CANN 社区现有项目和相关 SIG；
- 本 SIG 与 recipes SIG 协同建设具身智能样例。recipes SIG 侧重通用算法样例与最佳实践，Embodied-AI SIG 侧重具身智能领域的完整技术体系、统一规范、真实硬件验证及相关仓库治理；
- 已有具身智能样例的迁移和归属将按照双方协作结果及 CANN 社区治理流程推进。

## 成员

### Maintainer 列表

- 高阳 [@NJU_GaoYang](https://gitcode.com/NJU_GaoYang), *gaoy@nju.edu.cn*
- 徐凯 [@IAII_XuKai](https://gitcode.com/IAII_XuKai), *kxu@iaii.ac.cn*
- 张伟男 [@weinanzhang](https://gitcode.com/weinanzhang), *wnzhang@ir.hit.edu.cn*

### Committer 列表

- 赵昊 [@fromandto](https://gitcode.com/fromandto), *zhaohao@air.tsinghua.edu.cn*
- 霍静 [@JingHuo](https://gitcode.com/JingHuo), *huojing@nju.edu.cn*
- 龙霄潇 [@xxlong](https://gitcode.com/xxlong), *xxlong@nju.edu.cn*
- 黄虎 [@huanghu7](https://gitcode.com/huanghu7), *huanghu7@126.com*
- 史桀绮 [@NJU_JIEQI](https://gitcode.com/NJU_JIEQI), *isjieqi@nju.edu.cn*
- 李文斌 [@NJU_WenbinLi](https://gitcode.com/NJU_WenbinLi), *liwenbin@nju.edu.cn*
- 陈子璇 [@NJU_Zixuan](https://gitcode.com/NJU_Zixuan), *chenzx@nju.edu.cn*
- 黄伟 [@huangwayne28](https://gitcode.com/huangwayne28), *huangwei188@hisilicon.com*
- 张心放 [@rous_zhang](https://gitcode.com/rous_zhang), *zhangxinfang5@hisilicon.com*
- 甄泰航 [@NJU_Taihang](https://gitcode.com/NJU_Taihang), *taihangzhen@smail.nju.edu.cn*
- 吴志平 [@NJU_zhiping](https://gitcode.com/NJU_zhiping), *zhipingwu@smail.nju.edu.cn*
- 吴优 [@NJU_YouWu](https://gitcode.com/NJU_YouWu), *you@smail.nju.edu.cn*
- 王沛杨 [@py_wang](https://gitcode.com/py_wang), *py_wang@smail.nju.edu.cn*
- 许昊 [@hao-xu](https://gitcode.com/hao-xu), *juevesxu@163.com*
- 龚靖尧 [@jy_gong](https://gitcode.com/jy_gong), *gongjy.cs@foxmail.com*
- 周杨程煜 [@NJU_ChuCheng](https://gitcode.com/NJU_ChuCheng), *zhouyangchengyu@whu.edu.cn*
- 王晶 [@NJU_JingWang](https://gitcode.com/NJU_JingWang), *221900040@smail.nju.edu.cn*
- 吕轩 [@xuan_lv](https://gitcode.com/xuan_lv), *xlvnudt@nudt.edu.cn*

其他 Committer 将在完成 GitCode 账号注册、CLA 签署和角色确认后，按照 CANN 社区治理流程逐步补充。

## 社区运作

### 会议组织

- 公开会议频率：北京时间，每月一次线上例会，具体时间以会议白板通知为准；
- [CANN 社区会议平台](https://meeting.osinfra.cn/cann/)
- [议题申报及会议纪要](https://etherpad-cann.meeting.osinfra.cn/p/sig-embodied-ai)

例会主要跟踪以下内容：

- SIG 仓库建设与技术路线；
- 模型样例迁移、适配和合入进展；
- Issue 和 Pull Request 处理情况；
- Benchmark、数据格式和硬件接口建设；
- 社区贡献者及成员增补；
- 与 CANN 社区其他 SIG 的协同事项。

### 邮件列表

- SIG 邮件列表：[embodied-ai@cann.osinfra.cn](mailto:embodied-ai@cann.osinfra.cn)

邮件列表用于发布会议通知、议程、会议纪要和 SIG 重要事项。

## 贡献指南

欢迎高校、科研机构、机器人企业和个人开发者参与 Embodied-AI SIG 共建。

社区成员可以通过以下方式参与：

- 在相关仓库提交 Issue，反馈问题、需求或改进建议；
- 提交 Pull Request，贡献代码、文档、模型样例和测试用例；
- 参与 SIG 例会，讨论技术路线、接口规范和项目进展；
- 贡献真实机器人验证案例、数据格式、评测基准和硬件适配方案；
- 参与昇腾平台上的模型迁移、性能分析和优化工作。

## 未来规划

### 启动阶段：2026 年 6 月—9 月

- 完成 SIG 组织和治理信息配置；
- 完成八个仓库创建并推进初始化；
- 建立仓库目录、文档和基础 CI 规范；
- 梳理团队硬件资源和首批模型适配任务。

### 落地阶段：2026 年 9 月—12 月

- 围绕操作、运动控制、导航和世界模型沉淀主流模型训推样例；
- 建立训练与部署样例的目录规范和文档模板；
- 推动首批真实机器人验证案例落地。

### 扩展阶段：2026 年 12 月—2027 年 3 月

- 扩展世界模型、3D 感知与重建相关样例；
- 发布具身智能 Benchmark 初版；
- 沉淀性能测试结果及面向 CANN 的需求反馈清单。

### 共建阶段：2027 年 3 月—6 月

- 发布具身智能教程和社区案例；
- 开展技术分享、高校交流和社区活动；
- 引入更多外部 Contributor；
- 形成 SIG 年度技术成果和社区案例集。

## License

SIG 所属仓库原则上采用 Apache License 2.0。所引用的上游模型、数据集及第三方组件遵循其各自许可证，并在对应仓库的 LICENSE 或 NOTICE 文件中进行说明。