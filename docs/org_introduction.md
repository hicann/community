
## 开源项目

<table style="width:100%">
  <tr>
    <th style="width:10%"><span style="font-size:17px;">组件</span></th>
    <th style="width:75%"><span style="font-size:17px;">描述</span></th>
	  <th style="width:15%"><span style="font-size:17px;">源码仓</span></th>
  </tr>
    <tr>
    <td><span style="font-size:16px;">算子库</span></td>
    <td><span style="font-size:16px;">提供了丰富的深度优化、硬件亲和的高性能算子，为神经网络在昇腾硬件上加速计算提供基础。</span></td>
	<td>
      <a href="https://gitcode.com/cann/ops-nn"><span style="font-size:16px;">ops-nn</span></a><br>
      <a href="https://gitcode.com/cann/ops-math"><span style="font-size:16px;">ops-math</span></a><br>
      <a href="https://gitcode.com/cann/ops-transformer"><span style="font-size:16px;">ops-transformer</span></a><br>
       <a href="https://gitcode.com/cann/ops-cv"><span style="font-size:16px;">ops-cv</span></a></td>
  </tr>
  <tr>
    <td><span style="font-size:16px;">通信库</span></td>
    <td><span style="font-size:16px;">基于昇腾硬件的高性能通信库，提供单机多卡及多机多卡间的数据并行、模型并行通信方案。</span></td>
	<td><a href="https://gitcode.com/cann/hixl"><span style="font-size:16px;">hixl</span></a><br>
      <span style="font-size:16px;">hccl(建设中)</span></a><br>
      <span style="font-size:16px;">hcomm(建设中)</span></a><br>
       </td>
  </tr>
  <tr>
    <td><span style="font-size:16px;">图引擎</span></td>
    <td><span style="font-size:16px;">计算图编译和运行的控制中心，提供图优化、图编译管理以及图执行控制等功能。</span></td>
		<td><a href="https://gitcode.com/cann/graph-autofusion"><span style="font-size:16px;">graph-autofusion</span></a><br>
      <span style="font-size:16px;">ge(建设中)</span></a><br>
  </tr>
  <tr>
    <td><span style="font-size:16px;">编程语言</span></td>
    <td><span style="font-size:16px;">CANN针对算子开发场景推出的编程语言，最大化匹配用户开发习惯，提供算子模板库，支持算子极简编程。</span></td>
    <td><a href="https://gitcode.com/cann/atvc"><span style="font-size:16px;">atvc</span></a><br>
      <span style="font-size:16px;">asc-devkit(建设中)</span><br>
    </td>
  </tr>
   <tr>
    <td><span style="font-size:16px;">运行时</span></td>
    <td><span style="font-size:16px;">提供了高效的硬件资源管理、媒体数据预处理、单算子加载执行、模型推理等开发接口，供开发者轻松构建高性能人工智能应用。</span></td>
	<td><span style="font-size:16px;">建设中</span></td>
  </tr>
</table>


## 关于社区
### 社区治理架构及章程

CANN 社区采用分层协作的治理模式，当前架构主要包括以下组织：

  - [技术指导委员会（TSC-Technical Steering Committee）](../CANN/TSC/README.md)
  - [项目管理委员会（PMC-Project Management Committee）](../CANN/PMC/README.md)
  - [特别兴趣小组（SIG-Special Interest Group）](https://gitcode.com/cann/community/tree/master/CANN/sigs)

更多社区治理内容，详见：[社区治理章程](../README.md#社区治理章程)

### 参与贡献
  -  [基础贡献](../README.md#基础贡献)：包含参与社区会议、社区邮件讨论、提交 Issue 、处理 Issue 任务、提交PR等。
  -  [进阶贡献](../README.md#进阶贡献)：包含新建 SIG、成为核心贡献者、组织会议、新建仓库、引入开源软件、发布新版本或新仓库等。

## 快速体验

若您希望快速体验CANN算子的调用和开发过程，请访问如下文档获取简易教程。

- [算子调用](https://gitcode.com/cann/ops-math/blob/master/docs/invocation/quick_op_invocation.md)：介绍调用算子的基本步骤，快速搭建环境，实现算子编译执行。
- [算子开发](https://gitcode.com/cann/ops-math/blob/master/docs/develop/quick_op_develop.md)：介绍开发算子的基本流程，一键创建算子工程目录，实现Tiling、Kernel核心交付件。

## 实践样例

⚓[推理(cann-recipes-infer)](https://gitcode.com/cann/cann-recipes-infer) &nbsp; | &nbsp;🚈 [训练(cann-recipes-train)](https://gitcode.com/cann/cann-recipes-train)

|热门实践  |描述  |
|--|--|
|[DeepSeek-V3.2-Exp模型支持0day推理部署](https://gitcode.com/cann/cann-recipes-infer/blob/master/models/deepseek-v3.2-exp/README.md)  | 基于Transformers库，在Atlas A3环境中Prefill阶段采用了长序列亲和的CP并行策略，Decode阶段沿用大EP并行，同时整网设计新的NPU融合Kernel和多流并行优化，实现较高的吞吐推理性能。 |
|[DeepSeek-R1 RL训练优化实践](https://gitcode.com/cann/cann-recipes-train/blob/master/rl_train/deepseek/README.md)  | 基于开源veRL框架，搭配MindSpeed+vLLM-Ascend框架，在Atlas A3集群实现GRPO算法的高吞吐RL训练，并达到120TPS/卡的系统吞吐量。 |
|[HunyuanVideo模型推理优化实践](https://gitcode.com/cann/cann-recipes-infer/blob/master/models/HunyuanVideo/README.md)  | 基于xDiT框架，在Atlas A2环境中采用了Ulysses序列并行和RingAttention序列并行测量，同时适配了TeaCache加速，实现了较高的吞吐推理性能。 |



## 社区活动

- 🔥[CANN开源开放系列直播](../events/meetup/README.md)：大咖细剖开源政策和计划，maintainer全面解读热门开源项目。
- 🔥[昇腾AI算法挑战赛进阶赛](https://developer.huaweicloud.com/competition/information/1300000204)：昇腾AI算法挑战赛旨在汇聚全球各领域的优秀开发者同台竞技。开放昇腾AI计算平台的全栈能力与API资源，鼓励开发者构建高效创新的AI模型，解决实际场景问题。
- [社区会议日历](https://meeting.osinfra.cn/cann)：如果您对CANN社区的各类会议感兴趣，可访问会议日历。
-   [CANN训练营](https://www.hiascend.com/developer/activities/cann20252#cann-camp-2502-intro)：为开发者打造“学、练、赛、聘”成长体系：报名领取免费学习资源，每周一、四晚七点专家讲师[直播分享](https://www.hiascend.com/developer/activities/cann20252?tab=live)；通过[认证考核](https://www.hiascend.com/edu/certification/detail/34bf904cb410497cb9c582be6c047ff7)，参与[社区任务](https://gitcode.com/org/cann/discussions/22)赢华为三折叠等大奖。
- [昇腾AI创新大赛-算子挑战赛](https://www.hiascend.com/developer/ops)：昇腾AI创新大赛-算子挑战赛旨在培养一批精通Ascend C算子开发的开发者，鼓励开发者基于CANN的基础能力进行深度创新与实践。



## 联系我们
-   [社区邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists)：选择需要订阅的组织（TSC/PMC/SIG等），填写相关信息，进行邮件订阅（邮件推送内容包含：会议通知、会议纪要、内容讨论等），如果您对相关组织有诉求或者问题，也可以通过邮箱途径联系。
- 昇腾CANN（社交媒体）

  |<center><a href="https://space.bilibili.com/1190614918?spm_id_from=333.337.0.0">B站</a></center> | <center>微信公众号</center> | <center><a href="https://www.zhihu.com/people/ha-ha-ha-ha-51-33-24">知乎</a></center> |<center><a href="https://blog.csdn.net/m0_71340392">CSDN</a></center>|
  |--|--|--|--|
  | <img src="https://raw.gitcode.com/user-images/assets/7860879/9801d95a-df2b-45ee-acfe-4700466bb185/昇腾CANN_B站二维码.png" width="130" height="130" alt="cann_bilibili">  | <img src="https://raw.gitcode.com/user-images/assets/7860879/5bb520d4-98a6-425c-aa54-d95dd8a7c8fa/昇腾CANN微信公众号.jpg" width="130" height="130" alt="CANN微信公众号">| <img src="https://raw.gitcode.com/user-images/assets/7860879/a4aec200-c71b-4340-80c4-c22cbad5057f/zhihu.png" width="130" height="130" alt="昇腾CANN知乎"></a> | <img src="https://raw.gitcode.com/user-images/assets/7860879/8a47d24c-0a33-4ab7-9fb9-252771a90b47/CSDN.png" width="130" height="130" alt="昇腾CANN_CSDN"> |

- [cann@cann.team](mailto:cann@cann.team)



## 相关链接
- [昇腾社区](https://www.hiascend.com/cann)


