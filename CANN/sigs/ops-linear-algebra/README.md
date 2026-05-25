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
- ops-sparse（稀疏线性代数算子）
    - 定位：NPU提供稀疏线性代数能力，覆盖通用稀疏乘加与结构化/块稀疏等高阶稀疏计算路线。
    - 功能：面向 CSR、COO 等常见稀疏存储格式，提供稀疏矩阵–向量/矩阵乘（SpMV、SpMM 等）、稀疏–稠密混合计算、格式转换与稀疏相关基础算子，服务于科学计算与稀疏网络等场景。
- ops-solver（线性求解与分解算子）
    - 定位：NPU提供稠密与稀疏线性方程、矩阵分解及特征问题的数值求解能力。
    - 功能：覆盖线性方程组求解、矩阵分解（如 LU、Cholesky、QR 等典型路线）及特征值/奇异值等求解能力（具体 API 与能力以各版本文档为准），为仿真、优化与数值代数管线提供加速。

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
- 陈子忠 [@zizhongchen](https://gitcode.com/zizhongchen), *chenzizhong@cuhk.edu.cn*

## Committer列表
- 陈斌斌 [@chenbinbin199309](https://gitcode.com/chenbinbin199309), *chenbinbin20@huawei.com*
- 宋恺 [@songkai111](https://gitcode.com/songkai111), *songkai16@huawei.com*
- 赵颖超 [@zhaoyingchao2](https://gitcode.com/zhaoyingchao2), *zhaoyingchao2@hisilicon.com*
- 骆文 [@luowen203_gg123](https://gitcode.com/luowen203_gg123), *luowen16@huawei.com*
- 尹祺然 [@nino888](https://gitcode.com/nino888), *yinqiran1@huawei.com*
- 唐超 [@chaotang233](https://gitcode.com/chaotang233), *tangchao47@hisilicon.com*

# SIG订阅

- [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/ops-linear-algebra.cann.osinfra.cn/)

# 仓库清单

仓库地址：
- https://gitcode.com/cann/ops-blas
- https://gitcode.com/cann/ops-sparse
- https://gitcode.com/cann/ops-solver