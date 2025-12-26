
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
      <a href="https://gitcode.com/cann/ops-cv"><span style="font-size:16px;">ops-cv</span></a><br>
      <a href="https://gitcode.com/cann/atvoss"><span style="font-size:16px;">atvoss</span></a></td>
  </tr>
  <tr>
    <td><span style="font-size:16px;">通信库</span></td>
    <td><span style="font-size:16px;">基于昇腾硬件的高性能通信库，提供单机多卡及多机多卡间的数据并行、模型并行通信方案。</span></td>
	<td><a href="https://gitcode.com/cann/hixl"><span style="font-size:16px;">hixl</span></a><br>
      <a href="https://gitcode.com/cann/hccl"><span style="font-size:16px;">hccl</span></a><br>
      <a href="https://gitcode.com/cann/hcomm"><span style="font-size:16px;">hcomm</span></a><br>
       </td>
  </tr>
  <tr>
    <td><span style="font-size:16px;">图引擎</span></td>
    <td><span style="font-size:16px;">面向昇腾的图编译器和执行器，提供图优化、多流并行、内存复用和模型下沉等功能。</span></td>
   	<td><a href="https://gitcode.com/cann/ge"><span style="font-size:16px;">ge</span></a><br>
      <a href="https://gitcode.com/cann/metadef"><span style="font-size:16px;">metadef</span></a><br>
      <a href="https://gitcode.com/cann/graph-autofusion"><span style="font-size:16px;">graph-autofusion</span></a><br>
       </td> 
  </tr>
  <tr>
    <td><span style="font-size:16px;">编程语言</span></td>
    <td><span style="font-size:16px;">CANN针对算子开发场景推出的编程语言，最大化匹配用户开发习惯，提供算子模板库，支持算子极简编程。</span></td>
    <td>
      <a href="https://gitcode.com/cann/catlass"><span style="font-size:16px;">CATLASS</span></a><br>
      <a href="https://gitcode.com/cann/asc-devkit"><span style="font-size:16px;">asc-devkit</span></a><br>
      <a href="https://gitcode.com/cann/pyasc"><span style="font-size:16px;">pyasc</span></a><br>
      <a href="https://gitcode.com/cann/pypto"><span style="font-size:16px;">pypto</span></a><br>
    </td>
  </tr>
   <tr>
    <td><span style="font-size:16px;">运行时</span></td>
    <td><span style="font-size:16px;">提供了高效的硬件资源管理、媒体数据预处理、单算子加载执行、模型推理等开发接口，供开发者轻松构建高性能人工智能应用。</span></td>
	  <td><a href="https://gitcode.com/cann/runtime"><span style="font-size:16px;">runtime</span></a></td>
  </tr>
   <tr>
    <td><span style="font-size:16px;">驱动</span></td>
    <td><span style="font-size:16px;">提供了基础驱动、设备管理、资源管理及调度、通信能力等功能，使能昇腾芯片，充分发挥硬件能力，支撑CANN上层软件高效稳定运行。</span></td>
	  <td><a href="https://gitcode.com/cann/driver"><span style="font-size:16px;">driver</span></a><br> </td>
  </tr>
  <tr>
    <td><span style="font-size:16px;">工具</span></td>
    <td><span style="font-size:16px;">提供CANN平台的各种工具，如故障定位、模型压缩等。</span></td>
	  <td><a href="https://gitcode.com/cann/oam-tools"><span style="font-size:16px;">oam-tools</span></a><br>
    <a href="https://gitcode.com/cann/amct"><span style="font-size:16px;">amct</span></a>
    </td>
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

- [算子调用](https://gitcode.com/cann/ops-math/blob/master/docs/zh/invocation/quick_op_invocation.md)：介绍调用算子的基本步骤，快速搭建环境，实现算子编译执行。
- [算子开发](https://gitcode.com/cann/ops-math/blob/master/docs/zh/develop/aicore_develop_guide.md)：介绍开发算子的基本流程，一键创建算子工程目录，实现Tiling、Kernel核心交付件。

## 实践样例

⚓[推理](https://gitcode.com/cann/cann-recipes-infer) &nbsp; | &nbsp;🚈 [训练](https://gitcode.com/cann/cann-recipes-train) | &nbsp; 🔮 [空间智能](https://gitcode.com/cann/cann-recipes-spatial-intelligence) | &nbsp; 🎮 [具身智能](https://gitcode.com/cann/cann-recipes-embodied-intelligence) | &nbsp; 📱 [鸿蒙推理](https://gitcode.com/cann/cann-recipes-harmony-infer)

|热门实践  |描述  |
|--|--|
|[DeepSeek-V3.2-Exp模型支持0day推理部署](https://gitcode.com/cann/cann-recipes-infer/blob/master/models/deepseek-v3.2-exp/README.md)  | 基于Transformers库，在Atlas A3环境中Prefill阶段采用了长序列亲和的CP并行策略，Decode阶段沿用大EP并行，同时整网设计新的NPU融合Kernel和多流并行优化，实现较高的吞吐推理性能。 |
|[DeepSeek-R1 RL训练优化实践](https://gitcode.com/cann/cann-recipes-train/blob/master/llm_rl/deepseek/README.md)  | 基于开源veRL框架，搭配MindSpeed+vLLM-Ascend框架，在Atlas A3集群实现GRPO算法的高吞吐RL训练，并达到120TPS/卡的系统吞吐量。 |
|[HunyuanVideo模型推理优化实践](https://gitcode.com/cann/cann-recipes-infer/blob/master/models/HunyuanVideo/README.md)  | 基于xDiT框架，在Atlas A2环境中采用了Ulysses序列并行和RingAttention序列并行测量，同时适配了TeaCache加速，实现了较高的吞吐推理性能。 |
|[VGGT模型推理优化实践](https://gitcode.com/cann/cann-recipes-spatial-intelligence/blob/master/models/vggt/README.md)  | 基于VGGT开源模型，完成其在Atlas A2上的推理适配，并提供其在相机位姿估计、点云三维重建、深度估计三个任务上的精度评测脚本。 |
|[Pi0模型推理优化实践](https://gitcode.com/cann/cann-recipes-embodied-intelligence/blob/master/models/pi0/README.md)  | 基于LeRobot库，在Atlas A2环境适配Pi0模型，通过使能融合算子、图模式、计算逻辑优化等手段，实现了较低的推理时延。 |
|[QQ音乐声伴分离鸿蒙推理优化实践](https://gitcode.com/cann/cann-recipes-harmony-infer/blob/master/ops/ascendc/docs/custom-npu_bandNorm.md)  | 基于Ascend C实现QQ音乐声伴分离业务模型中的BandNorm等算子在Kirin 9030上的高性能推理部署。 |



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
- [鸿蒙社区](https://developer.huawei.com/consumer/cn/sdk/cann-kit/)


