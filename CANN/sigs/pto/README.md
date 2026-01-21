# pto SIG

## 概述

PTO是CANN推出的一款面向AI加速器的高性能编程系统，包括**PyPTO编程框架**和**PTO虚拟指令集**。
该系统旨在简化算子Kernel开发流程，提供高性能计算执行能力，并通过虚拟指令集实现硬件平台的可移植性。

该系统采用PTO（Parallel Tensor/Tile Operation）编程范式，以基于Tile的编程模型为核心设计理念。
通过多层次的计算图表达，将用户构建的AI模型应用从高层次计算图逐步编译成PTO虚拟指令，最终生成目标平台上高效执行的代码。

## 工作目标
- 1、负责PTO的技术路线规划和落地；
- 2、组织PTO例会，引导技术讨论和决策；
- 3、负责周边组织沟通协调，推动落地相关项目；
- 4、负责SIG 仓库权限和邮件列表等基础设施的管理；
- 5、负责社区Bug、issue和邮件列表等渠道反馈的问题分发处理。

## 职责与范围
本SIG主要负责以下仓库的开发与维护：

- [PyPTO框架](https://gitcode.com/cann/pypto)
    - 定位：提供基于Python的高性能算子开发框架
    - 功能：简化算子Kernel开发流程，提供Tile编程模型和计算图编译能力
- [PTO虚拟指令集](https://gitcode.com/cann/pto-isa)
    - 定位：提供硬件无关的虚拟指令集抽象
    - 功能：定义PTO虚拟指令规范，支持跨硬件平台的可移植性

# 成员

### Maintainer列表

- 林嘉树 [@linjiashu](https://gitcode.com/linjiashu), *linjiashu@huawei.com*
- 周若愚 [@zhoubotcam](https://gitcode.com/zhoubotcam), *ruoyu.zhou@hisilicon.com*
- 冯思远 [@syfeng](https://gitcode.com/syfeng), *syfeng@sii.edu.cn*
- 尹杰 [@yinjie27_](https://gitcode.com/yinjie27_), *yinjie27@huawei.com*
- 孙文博 [@gcw_9WvwSY5N](https://gitcode.com/gcw_9WvwSY5N), *sunwenbo1@huawei.com*

### Committer列表

#### PyPTO仓库: https://gitcode.com/cann/pypto

- 张中 [@foundea](https://gitcode.com/foundea), *zhangzhong5@huawei.com*
- 袁野 [@jason_yuan_ye](https://gitcode.com/jason_yuan_ye), *yuanye17@huawei.com*
- 杨旭 [@DCGDDD](https://gitcode.com/DCGDDD) *yangxu14@huawei.com*
- 李东升 [@tsungl4](https://gitcode.com/tsungl4), *lidongsheng4@huawei.com*
- 张广军 [@gguuaanngg](https://gitcode.com/gguuaanngg), *zhangguangjun2@huawei.com*
- 戴振韬 [@dai-zhentao](https://gitcode.com/dai-zhentao), *daizhentao1@hisilicon.com*
- 张越兵 [@zhangyuebing](https://gitcode.com/zhangyuebing), *zhangyuebing@hisilicon.com*
- 胡俊 [@cam_bxh](https://gitcode.com/cam_bxh), *Bee.hujun@huawei.com*
- 杲兴旺 [@gaoxingwang](https://gitcode.com/gaoxingwang), *camuel.gao@huawei.com*
- 林逸凡 [@lyfne](https://gitcode.com/lyfne), *linyifan@huawei.com*
- 陈鹏 [@poursoul](https://gitcode.com/poursoul), *chenpeng64@huawei.com*
- 张芷萁 [@hw_zhangzhiqi](https://gitcode.com/hw_zhangzhiqi), *zhangzhiqi14@huawei.com*
- 汪超 [@wcwxy](https://gitcode.com/wcwxy), *wangchao520@hisilicon.com*
- 陈章麒 [@zhangqi-chen](https://gitcode.com/zhangqi-chen), *zhangqi.chen@hisilicon.com*
- 庄佳威 [@jiawei_zhuang](https://gitcode.com/jiawei_zhuang), *zhuangjiawei@hisilicon.com*

#### PTO仓库: https://gitcode.com/cann/pto-isa

- 常先宇 [@changxianyu](https://gitcode.com/changxianyu), *changxianyu@hisilicon.com*
- 陈家乐  [@ChanKaLok](https://gitcode.com/ChanKaLok), *chan.ka.lok@huawei.com*
- 黄星源 [@HuangXingYuan_777](https://gitcode.com/HuangXingYuan_777), *huangxingyuan4@huawei.com*
- 陈金林 [@csjlchen](https://gitcode.com/csjlchen), *chenjinlin1@huawei.com*
- 章海剑 [@Zhanghaijian](https://gitcode.com/Zhanghaijian), *z.zhanghaijian@huawei.com*
- 瞿柯林 [@qukelin](https://gitcode.com/qukelin), *qukelin@huawei.com*
- 钱鑫海 [@bluesky901](https://gitcode.com/bluesky901), *qianxinhai@huawei.com*

# 社区运作

### 会议组织

- 公开的会议时间：北京时间，两周一次例会，双周(每月第二、第四周)周五下午14:00-16:00
- [议题申报](https://etherpad-cann.meeting.osinfra.cn/p/sig-pto)

### 会议纪要

- [会议地址](https://meeting.osinfra.cn/cann/)
- [会议纪要](https://etherpad-cann.meeting.osinfra.cn/p/sig-pto)

### 贡献指南

- [贡献指南](https://gitcode.com/cann/pypto/blob/master/CONTRIBUTION.md)

# SIG订阅

- [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/pto.cann.osinfra.cn/)

# 仓库清单

仓库地址：
- https://gitcode.com/cann/pypto
- https://gitcode.com/cann/pto-isa
