# community

欢迎体验CANN开源社区。

## CANN开源社区简介

Community仓主要承载关于CANN开源社区的相关信息，包括社区治理架构、组织介绍、用户行为准则、签署CLA、参与贡献等内容。

## 社区治理架构

如果您希望了解社区治理架构及章程，可以查看如下内容：
- [技术指导委员会（TSC-Technical Steering Committee）治理章程](governance/tsc-governance.md)
- [项目管理委员会（PMC-Project Management Committee）治理章程](governance/pmc-governance.md)
- [特别兴趣小组（SIG-Special Interest Group）治理章程](governance/sig-governance.md)
- [社区角色定义及晋升机制](governance/role-definition-and-promotion-mechanism.md)

## 组织介绍
- [技术指导委员会（TSC-Technical Steering Committee）](CANN/TSC/README.md)
- [项目管理委员会（PMC-Project Management Committee）](CANN/PMC/README.md)
- [特别兴趣小组（SIG-Special Interest Group）](CANN/sigs/)

## 用户行为准则

在参与贡献前，请了解社区[用户行为准则](contributor/code-of-conduct.md)，后续您在CANN开源社区的活动（包括但不限于发表评论、提交Issue、发表wiki等）都请遵循此行为准则。

## 签署CLA
在参与项目贡献前，您需要签署CANN开源社区贡献者许可协议（CLA）。请根据您的参与身份，选择签署个人CLA、员工CLA或企业CLA（点击[CLA签署](https://clasign.osinfra.cn/sign/68cbd4a3dbabc050b436cdd4)见详情）。

- **个人CLA**：如果你是一名独立开发者或者你所在的企业还未与社区签署企业CLA，请点击“签署个人CLA”进入CLA签署页面。
- **员工CLA**：如果你是作为一家已经签署了企业CLA的企业的员工共来签署CLA，请点击“法人贡献者登记”进入CLA签署页面；
- **企业CLA**：如果你是作为一家想要为社区贡献代码的企业来签署 CLA，请点击“ 签署法人CLA”进入CLA签署页面。

## 参与贡献
在签署了CLA协议、找到了想参与的开源项目后，就可以开始您的社区贡献之旅啦！贡献的方式有很多种，每一种贡献都将受到欢迎和重视。

### 提交Issue/处理Issue任务

- **查找Issue**：在您感兴趣的CANN开源项目GitCode主页内，点击“Issues”，即可找到 Issue 列表。

- **提交Issue**：如果您准备向社区上报Bug或者提交需求，或者为社区贡献自己的意见或建议，请在CANN开源项目对应的仓库上提交Issue。
  提交Issue请参考 [Issue提交指南](contributor/issue-submit.md)。

- **参与Issue讨论**：每个Issue下面都支持开发者们交流讨论，如果您感兴趣，可以在评论区中发表自己的意见。

- **处理Issue**：如果您愿意处理其中的一个issue，可以将它分配给自己。只需要在评论框内输入“/assign”或 “/assign @yourself”，机器人就会将问题分配给您，您的名字将显示在负责人列表里。
  
### 贡献编码
1. 准备CANN开发环境

   如果您想参与编码贡献，需要准备CANN开发环境，请参考每个开源项目的README.md，了解环境准备要求。

2. 了解CANN开源社区内的开发注意事项

    1）每个CANN开源项目使用的编码语言、开发编译环境等都可能存在差异，请参考每个开源项目中的README.md，了解编码贡献的一些要求。

    2）CANN开源项目软件编码遵循许可协议：CANN Open Software License Agreement Version 2.0，详细的协议说明请参见每个开源项目中的LICENSE文件，如果您贡献代码到CANN开源项目的源码仓是使用CANN Open Software License Agreement Version 2.0，请遵循此协议。

     请在新建的源码文件（包括cpp、py、h等文件）头部增加如下声明（其中版权信息可以由提交作者定义）：

     ```
     /**
      * This program is free software, you can redistribute it and/or modify it.
      * Copyright (c) 2025 Huawei Technologies Co., Ltd.
      * This file is a part of the CANN Open Software.
      * Licensed under CANN Open Software License Agreement Version 2.0 (the "License").
      * Please refer to the License for details. You may not use this file except in compliance with the License.
      * THIS SOFTWARE IS PROVIDED ON AN "AS IS" BASIS, WITHOUT WARRANTIES OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO NON-INFRINGEMENT, MERCHANTABILITY, OR FITNESS FOR A PARTICULAR PURPOSE.
      * See LICENSE in the root of the software repository for the full text of the License.
      */
     ```

3. 代码下载与贡献流程

![contri-flow.png](contributor/figures/contri-flow.png)

   1）进行代码开发前，请先将需要参与开发的仓库fork到个人仓，然后将个人仓下载到本地，并在本地分支进行代码修改。

   2）进行本地构建与验证，具体参考每个开源项目的说明文档。

   3）代码验证满足贡献要求后，提交Pull-Request，将代码贡献到相应的开源项目。

   4）参照[社区评论命令](docs/robot/cann/robot-command.md)中的对应命令触发门禁执行，并注意查看门禁测试结果，若未通过，请根据问题提示进行本地代码修改；若通过，此PR会被分配给committer检视，请关注committer的检视意见。

   5）当您的PR检视通过后，代码会合入相应的开源项目。

   关于GitCode工作流的详细操作可参见[GitCode工作流说明](contributor/gitcode-workflow.md)。

   当您在提交PR过程中遇到问题，常见问题的解决方法可参见[FAQs](docs/FAQ/infra-faqs.md)。

### 参与社区会议
如果您希望参加社区TSC/PMC/SIGs等组织会议，可以访问[社区会议看板](https://meeting.osinfra.cn/cann)获取更多信息，同时社区也为您提供了[相关模板](templates)用于社区交流材料编写。

### 教程与规范文档
- [CANN社区协作指南](https://gitcode.com/cann/community/blob/master/role-guidance.md)：所有角色的完整操作流程。
