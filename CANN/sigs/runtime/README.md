# runtime SIG

本SIG提供Ascend NPU资源管理和任务调度运行时(runtime)组件；维测功能组件(msprof, dump, trace)和基础组件(日志, mmpa, error_manager)。

## 工作目标

* 负责NPU运行时（Runtime）技术讨论，功能规划和开发。
* 负责维测功能组件的技术讨论，功能规划和开发。
* 负责SIG范围内的代码仓的Bug、Issuse和用户诉求等处理。

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
* 侯延保 [@hou-yanbao](https://gitcode.com/hou-yanbao), *[houyanbao@huawei.com](mailto:houyanbao@huawei.com)*
* 王涛 [@wangtao43](https://gitcode.com/wangtao43), *[wangtao43@huawei.com](mailto:wangtao43@huawei.com)*
* 罗宇舟 [@luoyuzhou2](https://gitcode.com/luoyuzhou2), *[luoyuzhou2@huawei.com](mailto:luoyuzhou2@huawei.com)*
* 翟沛超 [@ZhaiPeiChao](https://gitcode.com/ZhaiPeiChao), *[zhaipeichao@huawei.com](mailto:zhaipeichao@huawei.com)*
* 张磊 [@zlmay007](https://gitcode.com/zlmay007), *[re.zhanglei@huawei.com](mailto:re.zhanglei@huawei.com)*
* 温帆 [@Turing_JasonWen](https://gitcode.com/Turing_JasonWen), *[hw.wenfan@huawei.com](mailto:hw.wenfan@huawei.com)*
* 常海迅 [@changhaixun](https://gitcode.com/changhaixun), *[changhaixun@huawei.com](mailto:changhaixun@huawei.com)*
* 薛蕾 [@Axiaolei](https://gitcode.com/Axiaolei), *[xuelei1@huawei.com](mailto:xuelei1@huawei.com)*
* 曾益刚 [@gcw_9B2nSsjo](https://gitcode.com/gcw_9B2nSsjo), *[zengyigang@huawei.com](mailto:zengyigang@huawei.com)*
* 孙娜娜 [@sunnana_004434229](https://gitcode.com/sunnana_004434229), *[sunnana@huawei.com](mailto:sunnana@huawei.com)*
* 刘斌 [@liubin99](https://gitcode.com/liubin99), *[merlin.liubin@huawei.com](mailto:merlin.liubin@huawei.com)*
* 秦传瑜 [@qinchuanyu](https://gitcode.com/qinchuanyu), *[qinchuanyu@huawei.com](mailto:qinchuanyu@huawei.com)*
* 李良华 [@lilianghua_2025](https://gitcode.com/lilianghua_2025), *[lilianghua@huawei.com](mailto:lilianghua@huawei.com)*
* 沈勇武 [@huawei_programmer_011](https://gitcode.com/huawei_programmer_011), *[shenyongwu@huawei.com](mailto:shenyongwu@huawei.com)*
* 周武啸 [@zhou-wuxiao](https://gitcode.com/zhou-wuxiao), *[zhouwuxiao@hisilicon.com](mailto:zhouwuxiao@hisilicon.com)*
* 张金超 [@alenzhang86](https://gitcode.com/alenzhang86), *[zhangjinchao@huawei.com](mailto:zhangjinchao@huawei.com)*

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