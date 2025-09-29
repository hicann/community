
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
	<td><span style="font-size:16px;">建设中</span></td>
  </tr>
  <tr>
    <td><span style="font-size:16px;">图引擎</span></td>
    <td><span style="font-size:16px;">计算图编译和运行的控制中心，提供图优化、图编译管理以及图执行控制等功能。</span></td>
	<td><span style="font-size:16px;">建设中</span></td>
  </tr>
  <tr>
    <td><span style="font-size:16px;">编程语言</span></td>
    <td><span style="font-size:16px;">CANN针对算子开发场景推出的编程语言，最大化匹配用户开发习惯，提供算子模板库，支持算子极简编程。</span></td>
	<td><span style="font-size:16px;">建设中</span><span style="font-size:16px;"></span></td>
  </tr>
   <tr>
    <td><span style="font-size:16px;">运行时</span></td>
    <td><span style="font-size:16px;">提供了高效的硬件资源管理、媒体数据预处理、单算子加载执行、模型推理等开发接口，供开发者轻松构建高性能人工智能应用。</span></td>
	<td><span style="font-size:16px;">建设中</span></td>
  </tr>
</table>

## 快速入门

若您希望快速体验算子的调用和开发过程，请访问如下文档获取简易教程。

- [算子调用](https://gitcode.com/cann/ops-math/blob/master/docs/context/quick_op_invocation.md)：介绍调用算子的基本步骤，快速搭建环境，实现算子编译执行。
- [算子开发](https://gitcode.com/cann/ops-math/blob/master/docs/context/quick_op_develop.md)：介绍开发算子的基本流程，一键创建算子工程目录，实现Tiling、Kernel核心交付件。

## 热门样例 :
- [DeepSeek-V3.2-Exp模型在昇腾Atlas A3系列上已0day支持推理部署](https://gitcode.com/cann/cann-recipes-infer/blob/master/models/deepseek-v3.2-exp/README.md)：基于Transformers库，在Atlas A3环境中Prefill阶段采用了长序列亲和的CP并行策略，Decode阶段沿用大EP并行，同时从整网上设计了新的NPU融合Kernel和多流并行优化，实现了较高的吞吐推理性能。


## 会议日历

如果您对CANN社区的各类会议感兴趣，请访问[会议日历](https://meeting.osinfra.cn/cann/)。

## 社区活动
- [CANN训练营](https://www.hiascend.com/developer/activities/cann20251)：2025年CANN训练营全新升级，定制化四大专题直播课程，帮助不同阶段的开发者快速入门和提升Ascend C算子开发技术。
- [昇腾AI创新大赛-算子挑战赛](https://www.hiascend.com/developer/ops)：昇腾AI创新大赛-算子挑战赛旨在培养一批精通Ascend C算子开发的开发者，鼓励开发者基于CANN的基础能力进行深度创新与实践。

## 如何参与
- [社区介绍](https://gitcode.com/cann/community)

## 开发者论坛
- [昇腾论坛](https://www.hiascend.com/forum/forum-0106101385921175004-1.html)


## 合作联系

官方邮箱：cann@cann.team

## 相关链接
- [昇腾社区](https://www.hiascend.com/cann)
    