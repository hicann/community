# driver SIG

Driver SIG专注于 CANN 生态中驱动软件的设计、开发、维护与性能优化，提供基础驱动、设备管理、资源管理及调度、通信能力等功能，使能昇腾芯片，帮助 CANN 生态向更通用、更可扩展的方向演进。
Driver是连接runtime组件与NPU硬件的核心基础设施，是整个CANN软件栈中性能、稳定性与可用性的关键组件之一。


## 工作目标（Goals）
- **完善设备管理能力**

完善设备启动加载、初始化、设备状态管理、日志导出等基础功能，提升设备全生命周期管理能力。

- **增强内存管理及资源调度能力**

P2P、零拷贝、共享内存等跨机跨设备内存管理机制进一步完善；更高效任务下发能力。

- **提升通信能力**

更高效的跨机跨设备通信机制和访问能力。

## 工作愿景（Vision）

构建一个开放、透明、协作友好的CANN驱动社区，共同推进 AI 加速体系的基础设施革新。
充分发挥昇腾硬件能力，抽象设备管理、资源管理及调度等基础功能， 帮助 CANN 生态向更通用、更可扩展的方向演进。

我们正在寻找热爱底层技术、对高性能计算与系统软件充满激情的开发者、架构师与研究者。
如果你想：
- 参与构建全球领先的 NPU Driver
- 设计底层 API、调度系统、内存模型
- 推动开源社区的技术方向
- 在真实的高性能 AI 体系中贡献关键代码

那么 Driver SIG 将是最适合你的地方。让我们一起打造高性能、高稳定、持续演进的昇腾基础设施软件!




# 成员

### Maintainer列表

* 唐贵金 [@tangguijin](https://gitcode.com/tangguijin), *[tangguijin@huawei.com](mailto:tangguijin@huawei.com)*
* 潘玉园  [@Panyuyuan](https://gitcode.com/panyuyuan), *[panyuyuan@huawei.com](mailto:panyuyuan@huawei.com)*
* 郑飞 [@feizheng](https://gitcode.com/feizheng), *[feizheng@huawei.com](mailto:feizheng@huawei.com)*
* 李琦 [@qili93](https://gitcode.com/qili93), *[liqi259@huawei.com](mailto:liqi259@huawei.com)*

### Committer列表

* 缪超 [@StarMickey33](https://gitcode.com/StarMickey33), *[miaochao2@huawei.com](mailto:miaochao2@huawei.com)*
* 冯呈祥 [@ad_cx](https://gitcode.com/ad_cx), *[fengchengxiang@huawei.com](mailto:fengchengxiang@huawei.com)*
* 林永添 [@linyt_86](https://gitcode.com/linyt_86), *[linyongtian@huawei.com](mailto:linyongtian@huawei.com)*
* 徐心 [@xxwyhq0](https://gitcode.com/xxwyhq0), *[xuxin18@huawei.com](mailto:xuxin18@huawei.com)*
* 杨小渊 [@LiWei79](https://gitcode.com/yangxiaoyuan), *[yangxiaoyuan@huawei.com](mailto:yangxiaoyuan@huawei.com)*
* 晏名香 [@zhaozhixuan](https://gitcode.com/yanmingxiang), *[yanmingxiang@huawei.com](mailto:yanmingxiang@huawei.com)*
* 谢英太 [@RubickRT1](https://gitcode.com/RubickRT1), *[xieyingtai@huawei.com](mailto:xieyingtai@huawei.com)*
* 方天位 [@fangtianwei2025](https://gitcode.com/fangtianwei2025), *[fangtianwei@huawei.com](mailto:fangtianwei@huawei.com)*
* 李胜 [@lishengvictor](https://gitcode.com/lishengvictor), *[victor.lisheng@huawei.com](mailto:victor.lisheng@huawei.com)*

# 社区运作

### 会议组织

* 公开的会议时间：北京时间，两周一次例会，单周(每月第一、第三周，节假日跳过)周五下午16:30-17:30
* [议题申报](https://etherpad.meeting.osinfra.cn/p/sig-driver)

### 会议纪要

* [会议地址](https://meeting.osinfra.cn/cann/)
* [会议纪要](https://etherpad.meeting.osinfra.cn/p/sig-driver)

# SIG订阅

* [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/driver.cann.osinfra.cn/)

# 仓库清单

仓库地址：

* * [https://gitcode.com/cann/driver](https://gitcode.com/cann/driver)