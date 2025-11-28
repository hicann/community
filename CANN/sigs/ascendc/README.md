# Ascend C SIG
Ascend C是昇腾AI处理器专用的算子程序开发语言，基于C/C++扩展，遵循C/C++标准规范，提供底层芯片完备编程能力，支撑实现极致性能。此外，AscendC 也通过构建多级接口，满足多场景算子开发诉求，尽可能匹配业界开发习惯，提升算子开发效率。

# 工作目标
- 负责AscendC 多级编程接口（含Python前端）的规划、设计，满足多维场景算子开发诉求，兼顾效率和性能；
- 负责AscendC 编译能力、调试调优领域技术路线探讨和规划；
- 组织Ascend C 算子编程领域例会，引导技术讨论和决策。
- 负责AscendC 范围内的代码仓的Bug、Issue和用户诉求等处理。

# 项目路标
- 2025/11: 基于A2/A3 AscendC 能力全面开源开放；新增PyAsc提供Python前端完备编程能力；
- 2025/12: 基于A2/A3 AscendC 开放语言扩展层C API，提供业界类似的C API编程体验；
- 2026 上半年：
    - 基于A5 全面开放SIMT、SIMD/SIMT新同构编程、基于寄存器的SIMD编程能力；
    - 基于A2/A3/A5 基础API全面支持Tensor Tile API，基于Layout支持Tile编程；
    - PyAsc前端支持基于Layout实现Tensor编程，提供业界类似的Tensor编程体验；

# 成员

### Maintainer列表
- 诸葛洵[@xun_zhuge](https://gitcode.com/xun_zhuge), *zhugexun@hisilicon.com*
- 黄金华[@ascendhjh](https://gitcode.com/ascendhjh), *huangjinhua3@huawei.com*

### Committer列表
- 诸葛洵[@xun_zhuge](https://gitcode.com/xun_zhuge), *zhugexun@hisilicon.com*
- 顾欣欣[@ookkkkoo1122](https://gitcode.com/ookkkkoo1122), *guxinxin2@hisilicon.com*
- 高跃[@gao_dafa](https://gitcode.com/gao_dafa), *gaoyue6@huawei.com*
- 姜泽东[@jiangZD](https://gitcode.com/jiangZD), *jiangzedong2@hisilicon.com*
- 石楠翔[@shi_nanxiang](https://gitcode.com/shi_nanxiang), *shinanxiang@huawei.com*
- 王筱治[@wangxiaozhi](https://gitcode.com/wangxiaozhi), *wangxiaozhi2@huawei.com*
- 王涛[@wqtshg_wt](https://gitcode.com/wqtshg_wt), *wangtao123@huawei.com*
- 吴洋[@wuyang_hw](https://gitcode.com/wuyang_hw), *wuyang74@hisilicon.com*
- 杨厚玉[@houyuyang](https://gitcode.com/houyuyang), *yanghouyu@huawei.com*
- 杨滨华[@yangbinhua](https://gitcode.com/yangbinhua), *yangbinhua1@huawei.com*
- 杨学斌[@XuebinYang](https://gitcode.com/XuebinYang), *yangxuebin6@hisilicon.com*
- 廖晓辉[@sjtulxh](https://gitcode.com/sjtulxh), *liaoxiaohui3@hisilicon.com*
- 陈一源[@chenyiyuan](https://gitcode.com/chenyiyuan), *chenyiyuan5@huawei.com*
- 张浩[@zhanghao_0689](https://gitcode.com/zhanghao_0689), *zhanghao152@huawei.com*
- 邓静[@dengjing_aoe](https://gitcode.com/dengjing_aoe), *dengjing20@hisilicon.com*
- 叶珍妮[@YeZZzzz1](https://gitcode.com/YeZZzzz1), *yezhenni1@huawei.com*
- 黄铎[@DragonBornHD84](https://gitcode.com/DragonBornHD84), *huangduo4@hisilicon.com*
- 钱鑫海[@bluesky901](https://gitcode.com/bluesky901), *qianxinhai@huawei.com*
- 苏建加[@suqwe](https://gitcode.com/suqwe), *sujianjia@huawei.com*
- 孔琼卓[@kong0808](https://gitcode.com/kong0808), *kongqiongzhuo@huawei.com*
- 姜新誉[@jiangxinyu3](https://gitcode.com/jiangxinyu3), *jiangxinyu3@hisilicon.com*
- 朱梁英[@zhuliangying](https://gitcode.com/zhuliangying), *zhuliangying@huawei.com*
- 吴林玉[@wly451717](https://gitcode.com/wly451717), *wulinyu4@huawei.com*
- 傅珺[@fujun19](https://gitcode.com/fujun19), *fujun19@hisilicon.com*
- 闫庆尚[@yanqingshang](https://gitcode.com/yanqingshang), *yanqingshang@huawei.com*
- 艾鑫[@ai_xin](https://gitcode.com/ai_xin), *aixin2@hisilicon.com*
- 秦名扬[@qin437231](https://gitcode.com/qin437231), *qinmingyang@huawei.com*
- 苏统华[@sutonghua](https://gitcode.com/sutonghua), *tonghuasu@gmail.com*
- 武震卿[@wuzhenqing](https://gitcode.com/wuzhenqing), *wuzhenqing@stu.hit.edu.cn*

# 社区运作

### 会议组织

- 公开的会议时间：北京时间，两周一次例会，双周周五上午11:00-12:00
- [议题申报](https://etherpad.meeting.osinfra.cn/p/sig-ascendc)

### 会议纪要

- [会议地址](https://meeting.osinfra.cn/cann/)
- [会议纪要](https://etherpad.meeting.osinfra.cn/p/sig-ascendc)

# SIG订阅

- [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/ascendc.cann.osinfra.cn/)

# 仓库清单

仓库地址：
- https://gitcode.com/cann/atvc
- https://gitcode.com/cann/pyasc
- https://gitcode.com/cann/asc-devkit
- https://gitcode.com/cann/asc-tools