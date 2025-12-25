# runtime SIG

Runtime SIG专注于 CANN 生态中运行时的设计、开发、维护与性能优化。我们致力于构建一个高性能、可扩展、开放且面向未来的 AI 运行时系统，帮助 Ascend 生态向更通用、更可扩展、更友好的方向演进。

Runtime 是连接算子编译、图执行、调度器、通信库与NPU硬件的核心基础设施，是整个CANN软件栈中性能、稳定性与可用性最关键的组件之一。

在未来的生态中，我们希望CANN运行时不仅仅服务于框架和模型，更能成为产业级AI计算的统一执行底座。

## 工作目标（Goals）
- **开放并规范运行时API**

    使其适合 PyTorch、TensorFlow、MindSpore 以及未来的统一编程框架使用。

- **提升运行时的性能与确定性**

    Kernel高效下发和调度执行

    流调度更高效和可控

    更高的异步执行效率和加速器间的高效同步

    基于device CPU创新的调度机制

- **增强多设备、多机通信能力**

    P2P、零拷贝、共享内存等跨设备机制进一步开放

    Runtime 与 HCCL/SHMEM 的深度协同

- **全面完善错误体系、可观测性、调试能力**

    包含 Trace、Profiler、Dump、资源快照等。

## 工作愿景（Vision）

构建一个开放、透明、协作友好的CANN运行时社区，共同推进 AI 加速体系的基础设施革新。

推动Stream调度、任务调度、内存、事件、通信、集群执行等能力全面对齐国际主流架构，如 CUDA Runtime、ROCm Runtime，同时保留 Ascend 自身优势。

我们正在寻找热爱底层技术、对高性能计算与系统软件充满激情的开发者、架构师与研究者。
如果你想：
- 参与构建全球领先的 NPU Runtime
- 设计底层 API、调度系统、内存模型
- 优化 AICore、DMA、HCCS 的性能潜力
- 推动开源社区的技术方向
- 在真实的高性能 AI 体系中贡献关键代码

那么 Runtime SIG 将是最适合你的地方。让我们一起打造 开放、强大、可持续的 AI 运行时基础设施!




# 成员

### Maintainer列表

* 王涛 [@wangtao43](https://gitcode.com/wangtao43), *[wangtao43@huawei.com](mailto:wangtao43@huawei.com)*
* 张子菁  [@tingwood](https://gitcode.com/tingwood), *[zhangzijing@huawei.com](mailto:zhangzijing@huawei.com)*
* 许世峰 [@derekxu](https://gitcode.com/derekxu), *[derek.xu@huawei.com](mailto:derek.xu@huawei.com)*

### Committer列表

**runtime**

* 鄢海燕 [@turing_yhy](https://gitcode.com/turing_yhy), *[yanhaiyan@huawei.com](mailto:yanhaiyan@huawei.com)*
* 张朋朋 [@zhangpengpeng8](https://gitcode.com/zhangpengpeng8), *[zhangpengpeng8@hisilicon.com](mailto:zhangpengpeng8@hisilicon.com)*
* 雷欢 [@Reyn52166](https://gitcode.com/Reyn52166), *[leihuan1@huawei.com](mailto:leihuan1@huawei.com)*
* 晏名香 [@yanmingxiang](https://gitcode.com/yanmingxiang), *[yanmingxiang@huawei.com](mailto:yanmingxiang@huawei.com)*
* 李伟 [@LiWei79](https://gitcode.com/LiWei79), *[liwei174@huawei.com](mailto:liwei174@huawei.com)*
* 赵之轩 [@zhaozhixuan](https://gitcode.com/zhaozhixuan), *[zhaozhixuan2@hisilicon.com](mailto:zhaozhixuan2@hisilicon.com)*
* 王东安 [@wda1991](https://gitcode.com/wda1991), *[wangdongan@hisilicon.com](mailto:wangdongan@hisilicon.com)*
* 侯延保 [@houyanbao](https://gitcode.com/houyanbao), *[houyanbao@huawei.com](mailto:houyanbao@huawei.com)*
* 王涛 [@wangtao43](https://gitcode.com/wangtao43), *[wangtao43@huawei.com](mailto:wangtao43@huawei.com)*
* 罗宇舟 [@luoyuzhou2](https://gitcode.com/luoyuzhou2), *[luoyuzhou2@huawei.com](mailto:luoyuzhou2@huawei.com)*
* 翟沛超 [@ZhaiPeiChao](https://gitcode.com/ZhaiPeiChao), *[zhaipeichao@huawei.com](mailto:zhaipeichao@huawei.com)*
* 张磊 [@zlmay007](https://gitcode.com/zlmay007), *[re.zhanglei@huawei.com](mailto:re.zhanglei@huawei.com)*
* 温帆 [@Turing_JasonWen](https://gitcode.com/Turing_JasonWen), *[hw.wenfan@huawei.com](mailto:hw.wenfan@huawei.com)*
* 常海迅 [@changhaixun](https://gitcode.com/changhaixun), *[changhaixun@huawei.com](mailto:changhaixun@huawei.com)*
* 薛蕾 [@Axiaolei](https://gitcode.com/Axiaolei), *[xuelei1@huawei.com](mailto:xuelei1@huawei.com)*
* 曾益刚 [@gcw_9B2nSsjo](https://gitcode.com/gcw_9B2nSsjo), *[zengyigang@huawei.com](mailto:zengyigang@huawei.com)*
* 孙娜娜 [@sunnana_004434229](https://gitcode.com/sunnana_004434229), *[sunnana@huawei.com](mailto:sunnana@huawei.com)*
* 刘斌 [@liubin1986](https://gitcode.com/liubin1986), *[merlin.liubin@huawei.com](mailto:merlin.liubin@huawei.com)*
* 秦传瑜 [@qinchuanyu](https://gitcode.com/qinchuanyu), *[qinchuanyu@huawei.com](mailto:qinchuanyu@huawei.com)*
* 李良华 [@lilianghua_2025](https://gitcode.com/lilianghua_2025), *[lilianghua@huawei.com](mailto:lilianghua@huawei.com)*
* 沈勇武 [@huawei_programmer_011](https://gitcode.com/huawei_programmer_011), *[shenyongwu@huawei.com](mailto:shenyongwu@huawei.com)*
* 周武啸 [@zhou-wuxiao](https://gitcode.com/zhou-wuxiao), *[zhouwuxiao@hisilicon.com](mailto:zhouwuxiao@hisilicon.com)*
* 张金超 [@alenzhang86](https://gitcode.com/alenzhang86), *[zhangjinchao@huawei.com](mailto:zhangjinchao@huawei.com)*
* 陈伟伟 [@chen_vvjob](https://gitcode.com/chen_vvjob), *[chenweiwei22@huawei.com](mailto:chenweiwei22@huawei.com)*

**维测功能组件**

* 朱梁英 [@zhuliangying](https://gitcode.com/zhuliangying), *[zhuliangying@huawei.com](mailto:zhuliangying@huawei.com)*
* 傅珺 [@fujun19](https://gitcode.com/fujun19), *[fujun19@hisilicon.com](mailto:fujun19@hisilicon.com)*
* 陈豪 [@chenhao_1209](https://gitcode.com/chenhao_1209), *[chenhao61@huawei.com](mailto:chenhao61@huawei.com)*
* 张帆[@zhangfan\_hanq](https://gitcode.com/zhangfan_hanq), *[tonhi.zhangfan@huawei.com](mailto:tonhi.zhangfan@huawei.com)*

# 社区运作

### 会议组织

* 公开的会议时间：北京时间，两周一次例会，单周(每月第一、第三周，节假日跳过)周四下午14:00-16:00
* [议题申报](https://etherpad.meeting.osinfra.cn/p/sig-runtime)

### 会议纪要

* [会议地址](https://meeting.osinfra.cn/cann/)
* [会议纪要](https://etherpad.meeting.osinfra.cn/p/sig-runtime)

# SIG订阅

* [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/runtime.cann.osinfra.cn/)

# 仓库清单

仓库地址：

* * [https://gitcode.com/cann/runtime](https://gitcode.com/cann/runtime)