# ge SIG
# 概述
GE SIG是CANN图模式研发的兴趣小组，聚焦于图编译器的设计与演进，我们致力于打造开放、易用、性能领先的图编译基础设施，深度融入开源生态，让用户在主流框架获得稳定高效、持续演进的图模式体验。

# 工作目标
- 负责图框架领域技术路线探讨与规划。
- 组织图框架领域例会，引导技术讨论和决策。
- 负责SIG范围内的代码仓的Bug、Issue和用户诉求等处理。

# 职责范围与核心仓库
本SIG 主要负责以下几个核心仓库的开发与维护：

* ge
  * 定位：GE是计算图编译和运行的控制中心，提供图编译、图优化以及图执行控制等功能。GE通过统一的图开发接口支持多种AI框架的接入，并支持自定义图结构，帮助开发者在昇腾硬件上快速部署神经网络业务。GE可应用于大模型推理、推荐、小模型等领域。
  * 功能：图引擎核心仓，具备图编译和图执行的能力，功能上支持静态shape和动态shape，提供图融合优化、内存管理、资源管理、下沉调度等，接口上提供graph相关的API，支撑用户自主构图，运行图。

* metadef
  * 定位：昇腾元数据定义，即相关数据结构以及对外接口定义。
  * 功能：提供算子和图共用的基础数据结构以及接口，支持eager模式调用以及图模式调用。 

* graph-autofusion
  * 定位：面向昇腾（Ascend）芯片的轻量级、解耦式组件集合，旨在通过自动融合技术加速模型执行。 目前已开源 SuperKernel 组件，未来将持续开放更多融合相关模块。
  * 功能：基于 codegen 的 JIT 编译机制实现高效融合与加速。

* torchair
  * 定位：torchair（全称：Torch Ascend Intermediate Representation）是一个扩展库，支持用户基于PyTorch框架和torch_npu插件在昇腾NPU上使用图模式进行推理。 
  * 功能：TorchAir继承自PyTorch框架Dynamo模式，将PyTorch的FX图转换为GE计算图，并提供了GE计算图在昇腾NPU的编译与执行的能力。

* triton-inference-server-ge-backend
  * 定位：GE图模式使用的优秀实践，通过调用GE API，实现ge_backend的推理服务化框架，为用户如何使用GE提供了参考。 
  * 功能：ge-backend基于triton inference server框架实现对接NPU生态，快速实现传统CV\NLP模型的服务化。


# 边界与协作
本SIG负责的GE仓在CANN架构中位置如下图所示：

![alt text](image.png)

# 成员

### Maintainer列表
- 王涛[@wqtshg_wt](https://gitcode.com/wqtshg_wt), *wangtao123@huawei.com*
- 盛楠[@shengnan666](https://gitcode.com/shengnan666), *titan.sheng@huawei.com*

### Committer列表
- 唐群章[@tangqunzhang](https://gitcode.com/tangqunzhang), *tangqunzhang@huawei.com*
- 许亚非[@xuyafei](https://gitcode.com/xuyafei), *yxuyafei3@huawei.com*  
- 王笑天[@wangxiaotian995](https://gitcode.com/wangxiaotian995), *710309755@qq.com*
- 储星[@xchu42](https://gitcode.com/xchu42), *chuxing@huawei.com*
- 赵智慧[@zhaozhihui](https://gitcode.com/zhaozhihui), *zhaozhihui5@huawei.com*
- 李沛洋[@peiyang](https://gitcode.com/peiyang), *lipeiyang@huawei.com*
- 李宁[@lining23666](https://gitcode.com/lining23666), *lining.li@huawei.com*
- 耿超[@kobemini](https://gitcode.com/kobemini), *gengchao4@huawei.com*
- 黄桂军[@stevenaw0](https://gitcode.com/stevenaw0), *huangguijun@huawei.com*
- 詹隽[@zhanj](https://gitcode.com/zhanj), *zhanjun6@hisilicon.com*
- 薛鹏[@medivh-x](https://gitcode.com/medivh-x), *xuepeng4@huawei.com*
- 赵鑫鑫[@hugo111](https://gitcode.com/hugo111), *zhaoxinxin1@huawei.com*
- 张帆[@zhangfan_hanq](https://gitcode.com/zhangfan_hanq), *tonhi.zhangfan@huawei.com*
- 朱晶晶[@zhujingjing](https://gitcode.com/zhujingjing), *zhujingjing6@huawei.com*
- 楼衍廷[@louyanting](https://gitcode.com/louyanting), *louyanting@huawei.com*
- 魏晨光[@wei_chengaung](https://gitcode.com/wei_chengaung), *wei_chenguang@163.com*
- 丁炜秦[@dingweiqin_57](https://gitcode.com/dingweiqin_57), *d_viking@163.com*
- 劳大钊[@laodazhao1](https://gitcode.com/laodazhao1), *laodazhao@huawei.com*
- 杜宏祥[@LordOfMysteries](https://gitcode.com/LordOfMysteries), *15250980763@163.com*
- 袁野[@jason_yuan_ye](https://gitcode.com/jason_yuan_ye), *y1825181@163.com*
- 李培杰[@arthur_morgan_hw](https://gitcode.com/arthur_morgan_hw), *pjlee@aliyun.com*
- 李俊谕[@lijunyu_111](https://gitcode.com/lijunyu_111), *1005303540@qq.com*
- 刘伟[@liu-wei](https://gitcode.com/liu-wei), *ylovline.liuwei@huawei.com*
- 杨学斌[@XuebinYang](https://gitcode.com/XuebinYang), *yangxuebin@hisilicon.com*
- 廖晓辉[@sjtulxh](https://gitcode.com/sjtulxh), *liaoxiaohui3@hisilicon.com*
- 郭一伟[@guoyiwei1111](https://gitcode.com/guoyiwei1111), *guoyiwei2@huawei.com*
- 于海涛[@yuht9](https://gitcode.com/yuht9), *yuhaitao6@huawei.com*
- 傅骏[@fu-jun2](https://gitcode.com/fu-jun2), *fujun2@huawei.com*
- 顾康[@qq_28230035](https://gitcode.com/qq_28230035), *gukang3@huawei.com*
- 江潇[@jxkongyue](https://gitcode.com/jxkongyue), *jiangxiao2@huawei.com*

# 社区运作

### 会议组织

- 公开的会议时间：北京时间，两周一次例会，单周周五下午14:00-16:00
- [议题申报](https://etherpad.meeting.osinfra.cn/p/sig-ge)

### 会议纪要

- [会议地址](https://meeting.osinfra.cn/cann/)
- [会议纪要](https://etherpad.meeting.osinfra.cn/p/sig-ge)

# SIG订阅

- [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/ge.cann.osinfra.cn/)

# 仓库清单

仓库地址：
- https://gitcode.com/cann/graph-autofusion
- https://gitcode.com/cann/triton-inference-server-ge-backend
