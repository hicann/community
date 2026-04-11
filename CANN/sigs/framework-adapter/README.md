# framework-adapter SIG

## 概述

欢迎来到 **framework-adapter SIG**！我们聚焦 AI 框架与昇腾芯片的深度适配，实现主流框架对**昇腾硬件的原生支持**，在确保语义一致性与高性能的同时，**提高用户易用性并降低迁移成本**。

## 工作目标

- 推动第三方框架在昇腾硬件上的原生支持，在获得高性能的同时兼顾易用性，降低开发者的迁移成本。
- 通过例会、设计评审与技术分享，形成可复用的设计共识与最佳实践。
- 维护 SIG 范围内核心仓库的 Issue、Bug 与用户反馈，保障社区的响应效率与工程质量。

## 职责范围与核心仓库

本SIG 主要负责以下几个核心仓库的开发与维护：

- torchtitan-npu
  - **定位**：torchtitan-npu 是面向昇腾NPU亲和的训练系统框架，支持大模型训练中的内存、并行、调度与编译协同等关键能力。
  - **功能**：torchtitan-npu 基于 TorchTitan 的训练流程，在昇腾平台上提供稳定、可复现且可分析的训练框架，用于支撑真实大模型训练负载。仓库围绕训练阶段的关键系统能力，协同运行时与编译栈，实现内存管理、分布式并行、执行调度、算子融合与图优化路径等技术的工程化落地，并提供面向训练性能的分析与调优能力。同时，继承了TorchTitan原生的易用性优势。

- xla-npu
  - **定位**：xla-npu 是一个面向华为昇腾 NPU（Neural Processing Unit）硬件的 XLA（Accelerated Linear Algebra）后端实现。本项目通过接入OpenXLA/XLA开源项目，将XLA开源生态与华为 CANN（Compute Architecture for Neural Networks）软件栈集成，对接JAX框架。JAX框架运行时可以直接加载 xla-npu，使得基于JAX框架开发的模型可以运行在昇腾 NPU 上，提供推理场景图编译加速能力。
  - **功能**：xla-npu 实现 OpenXLA PJRT 运行时接口，通过调用CANN软件栈中 Runtime 接口管理设备、Stream、Event、内存等，从而驱动 NPU 设备运行模型；同时对接CANN生态中 Graph Engine、AFIR等编译后端，实现图编译。JAX 框架通过加载 xla-npu 动态库so文件，实现JAX框架对接NPU设备，运行JAX脚本及网络。


## SIG成员（Members）

### Maintainer列表

- 钟林[@zhonglin](https://gitcode.com/zhonglin), *echo.zhonglin@huawei.com*
- 盛楠[@shengnan666](https://gitcode.com/shengnan666), *titan.sheng@huawei.com*
- 张德鹏[@depeng1994](https://gitcode.com/depeng1994), *zhangdepeng2@huawei.com*
- 徐道鸿[@XDaoHong](https://gitcode.com/XDaoHong), *xudaohong@huawei.com*

### Committer列表

- 张昊卓[@zhanghz1](https://gitcode.com/zhanghz1), *zhanghaozhuo1@hisilicon.com*
- 许虞俊[@xuyujun](https://gitcode.com/xuyujun), *xuyujun5@hisilicon.com*
- 位金弈[@lrwei0709](https://gitcode.com/lrwei0709), *weijinyi3@huawei.com*
- 潘超[@panchao-gitcode](https://gitcode.com/panchao-gitcode), *panchao13@huawei.com*
- 梅贤昌[@gcw_w18ytwbi](https://gitcode.com/gcw_w18ytwbi), *meixianchang@huawei.com*
- 朱珉[@JaydenChu](https://gitcode.com/JaydenChu), *zhumin54@huawei.com*
- 栾超伟[@luanchaowei](https://gitcode.com/luanchaowei), *luanchaowei3@huawei.com*
- 邢智雄[@xingzhixiong](https://gitcode.com/xingzhixiong), *xingzhixiong@huawei.com*


## 社区运作

### 会议组织

- 公开的会议时间：北京时间，每两周一次例会，单周周三上午10:30-12:00
- [议题申报](https://etherpad-cann.meeting.osinfra.cn/p/sig-framework-adapter)

欢迎社区成员提交**技术讨论、设计提案、问题反馈或经验分享**等作为会议议题。

### 会议纪要

- [会议地址](https://meeting.osinfra.cn/cann/)
- [会议纪要](https://etherpad-cann.meeting.osinfra.cn/p/sig-framework-adapter)

## SIG订阅

- [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/framework-adapter.cann.osinfra.cn/)

## 仓库清单
仓库地址：
- https://gitcode.com/cann/torchtitan-npu
- https://gitcode.com/cann/xla-npu