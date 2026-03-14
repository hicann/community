# ops-linear-algebra SIG
算子线性代数领域相关的兴趣小组，负责线性代数基础算子能力建设与维护，如BLAS标准相关线性代数等算子。

## 工作目标
- 1、负责线性代数算子领域技术路线规划和落地；
- 2、组织线性代数算子领域例会，引导技术讨论和决策；
- 3、负责周边组织沟通协调，推动落地相关项目；
- 4、负责SIG 仓库权限和邮件列表等基础设施的管理；
- 5、负责社区Bug、issue和邮件列表等渠道反馈的问题分发处理。

## 职责与范围
本SIG主要负责[ops-blas](https://gitcode.com/cann/ops-blas)、[ops-solver](https://gitcode.com/cann/ops-solver)、[ops-sparse](https://gitcode.com/cann/ops-sparse) 这三个仓的开发与维护：
- ops-blas(基础线性代数算子)
    - 定位：NPU加速的BLAS（Basic Linear Algebra Subprograms）标准实现。
    - 功能：提供与 CPU BLAS 兼容的 API（aclblasSgemm等）以及现代灵活接口 aclBLASLt，支持混合精度、融合后处理、启发式算法选择等高级特性。
- ops-sparse
- ops-solver

# 社区运作

## 组织会议：
双周例会，每双周周四 14:00-16:00 (北京时间)
- [会议链接](https://meeting.osinfra.cn/cann/)
- [会议议题&纪要](https://etherpad-cann.meeting.osinfra.cn/p/sig-ops-linear-algebra)
- [邮件列表订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/ops-linear-algebra.cann.osinfra.cn/)

## 贡献指南
- [贡献指南](CONTRIBUTING.md)

# 成员

## Maintainer列表
- 王子韬 [@wangzitao_leo](https://gitcode.com/wangzitao_leo), *wangzitao4@huawei.com*
- 朱志明 [@QK_25415](https://gitcode.com/QK_25415), *zhuzhiming1@huawei.com*
- 唐超力 [@MaskHunter2008](https://gitcode.com/MaskHunter2008), *tangchaoli@huawei.com*
- 张浩 [@demoauguste](https://gitcode.com/demoauguste), *zhanghao418@huawei.com*

# SIG订阅

- [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/ops-linear-algebra.cann.osinfra.cn/)

# 仓库清单

仓库地址：
- https://gitcode.com/cann/ops-blas
- https://gitcode.com/cann/ops-sparse
- https://gitcode.com/cann/ops-solver