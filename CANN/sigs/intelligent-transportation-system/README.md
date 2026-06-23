# Intelligent Transportation System SIG

## 概述

Intelligent Transportation System SIG 是 CANN 社区面向智能交通系统领域的垂直兴趣小组，聚焦交通大数据分析、交通网络优化计算、交通大模型智能决策等场景，推进智能交通系统领域算子库、工具链和示例应用在 CANN 生态中的建设与落地。

本 SIG 旨在联合交通行业企业、高校、科研机构和开发者，围绕智能交通系统中的高性能计算、交通仿真、模型训练稳定性、交通智能体决策闭环等关键问题，沉淀可复用的开源代码仓、接口规范、样例任务和基础测试流程，为智慧路口、车路协同、智能网联、交通管控决策等场景提供可扩展的技术支撑。

## 工作目标

* 建设面向智能交通系统领域的开源代码仓，形成可复用的算子、工具、样例和文档；
* 推进交通大数据分析、交通网络优化计算和交通大模型智能决策等方向与 CANN 生态的适配；
* 组织 SIG 例会，开展技术讨论、任务分解、阶段成果评审和社区协作；
* 推动高校、科研机构、交通企业和开发者共同参与 CANN 智能交通系统领域生态建设；
* 维护 SIG 相关仓库、成员信息、会议入口、邮件列表和社区协作流程；
* 处理社区 Issue、PR、邮件列表等渠道反馈的问题。

## 职责与范围

Intelligent Transportation System SIG 初期主要围绕以下三个方向开展建设。

### its-matrix-computation

`its-matrix-computation` 面向昇腾平台矩阵计算优化场景，聚焦 GEMM 分块策略自动优化，解决矩阵尺寸复杂、参数空间离散、人工调优效率低等问题。

该方向将围绕 GEMM 分块策略、数据搬运路径、硬件执行约束和性能建模关系，探索从问题建模、约束感知搜索到跨任务经验迁移的一体化优化能力，提升矩阵计算任务在昇腾平台上的执行效率。

### its-stable-llm

`its-stable-llm` 面向大模型训练稳定性分析场景，聚焦微批次损失分布建模、失稳前兆识别和训练动态追踪。

该方向将 step-level 均值监控下沉到 micro-batch 分布建模，识别尾部扩张、局部分化、分布扭曲和训练动态异常等信号，在不显著增加训练开销的前提下，为大模型训练提供轻量化稳定性分析能力。

### its-trip

`its-trip` 面向交通大模型智能决策闭环场景，构建“感知—研判—仿真—下发”的闭环智能决策机制。

该方向将连接交通事件理解、知识调取、风险研判、方案生成、仿真验证和管控下发等环节，推动交通大模型从单点问答走向可验证、可执行、可落地的行业应用。

## 成员

### Maintainer 列表

* 王丽健 @wanglijian_zjec
* 刘志远 @zhiyuanliu
* 刘少韦华 @liushaoweihua1225

### Committer 列表

* 张玉杰 @seventeenzhang17z
* 孙虎成 @hucheng0222
* 安琨 @Candice_Kun_An
* 刘洋 @ly_evtech
* 王正礼 @wzlnju
* 顾子渊 @ZG_SEU
* 黄迪 @dihuangseu
* 黄凯 @huangkai0410
* 陈垚 @chenyao0303
* 徐占东 @ZhandongXu
* 张宏刚 @Zhang_Honggang
* 周臻 @zhenz2020
* 辛云鹏 @yx_xlqy
* 李宏 @HongriJiujiu

## 仓库清单

* [its-matrix-computation](https://gitcode.com/cann/its-matrix-computation)
* [its-stable-llm](https://gitcode.com/cann/its-stable-llm)
* [its-trip](https://gitcode.com/cann/its-trip)

## 社区运作

### 会议组织

* 公开会议时间：北京时间，两周一次例会，单周周五下午 14:00—14:30，节假日顺延或跳过。
* 会议议题和纪要入口将在 SIG 基础设施配置完成后补充。

### 邮件列表

* [intelligent-transportation-system@cann.osinfra.cn](mailto:intelligent-transportation-system@cann.osinfra.cn)

## 贡献指南

欢迎交通行业企业、高校、科研机构和开发者围绕交通大数据分析、交通网络优化计算、交通大模型智能决策、昇腾平台适配与优化等方向提交 Issue、PR、样例和技术文档。

参与者可通过以下方式参与 SIG 共建：

* 在相关仓库提交 Issue，反馈问题、需求或改进建议；
* 提交 Pull Request，贡献代码、文档、样例和测试；
* 参与 SIG 例会，讨论技术路线、任务进展和阶段成果；
* 围绕智能交通系统场景贡献可复用的数据处理、计算优化、模型训练稳定性分析和智能体决策流程示例。

## 未来规划

Intelligent Transportation System SIG 将按照基础建设、场景落地、生态深化三个阶段推进。

### 基础建设阶段

* 完成 `its-matrix-computation`、`its-stable-llm`、`its-trip` 三个核心仓库的规范化建设；
* 建立统一工程目录、接口规范、输入输出格式和基础测试流程；
* 梳理 GEMM 分块优化、微批次稳定性分析、交通智能体编排等核心能力；
* 完成与 CANN 社区的初步适配，形成可运行样例、README 文档和基础测试说明。

### 场景落地阶段

* 围绕高速路网在线推演、交通管控决策、交通智能体应用等场景开展验证；
* 打通交通大模型“感知—研判—仿真—下发”闭环流程；
* 推动智能交通系统领域算法、工具链和示例应用在 CANN 生态中的落地。

### 生态深化阶段

* 完善算子库高级功能，包括自动参数搜索、模型压缩、稳定性诊断、智能体流程编排等；
* 建立课程牵引和社区协作相结合的开发者贡献机制；
* 联合交通企业、科研机构和 CANN 社区开发者，形成持续迭代的代码共建机制；
* 发布智能交通系统领域 SIG 年度成果包，包括代码仓、样例任务、技术文档和场景验证报告。
