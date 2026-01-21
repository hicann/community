# CATLASS SIG

CATLASS，中文名为昇腾算子模板库，是一个聚焦于提供高性能矩阵乘类算子基础模板的代码库。本SIG负责确定 CATLASS 的版本规划与技术方案。

CATLASS 通过抽象分层的方式将矩阵乘及相关融合算子的实现代码模板化。算子实现可利用已提供的模板组件白盒化组装，模板组件可复用、替换或局部定制修改。各模板组件针对昇腾硬件特点设计，可支持FA等复杂算子运算逻辑在昇腾硬件上的高效流水排布，在上层代码逻辑共享的同时支持面向底层硬件的差异性特化。

CATLASS API 架构图：

<img src="../../../figures/sig/catlass_api_level.png" alt="架构图"  width="80%">

## 工作目标

- 规划与设计 CATLASS 组件模板、算子样例，覆盖多样化的 Gemm 算子开发场景、更全面的昇腾硬件，提升开发效率，提供定制场景极致性能优化案例；
- 组织 CATLASS 技术例会，推动技术讨论与决策落地；
- 处理 CATLASS 相关代码仓的缺陷、问题及用户反馈，响应用户诉求。

## Maintainer列表

- 周浩[@zhouhao176](https://gitcode.com/zhouhao176), *<zhouhao176@huawei.com>*
- 黄鑫[@huangxin361](https://gitcode.com/huangxin361), *<huangxin36@huawei.com>*
- 田行辉[@tianxinghui](https://gitcode.com/tianxinghui), *<tianxinghui@huawei.com>*

## 仓库清单

- ### CATLASS: [https://gitcode.com/cann/catlass](https://gitcode.com/cann/catlass)

- #### 简介：CATLASS 算子模板库主仓，提供 CATLASS 算子模板头文件、使用样例及调试工具等

- #### Committer列表

  - 周建伟[@zjw666888](https://gitcode.com/zjw666888), *<zhoujianwei4@huawei.com>*
  - 张云淞[@triwooder](https://gitcode.com/jtriwooder), *<zhangyunsong3@huawei.com>*
  - 祝松祥[@weixin_42818618](https://gitcode.com/weixin_42818618), *<zhusongxiang1@huawei.com>*
  - 陶源[@yuantao_](https://gitcode.com/yuantao_), *<taoyuan15@h-partners.com>*
  - 龙吉晖[@longjihui](https://gitcode.com/longjihui), *<longjihui@huawei.com>*
  - 孙昊[@sunhao_hw](https://gitcode.com/sunhao_hw), *<sunhao164@h-partners.com>*
  - 金修浪[@jxlang](https://gitcode.com/jxlang), *<jinxiulang@huawei.com>*
  - 徐汉儒[@hanru-xu](https://gitcode.com/hanru-xu), *<xuhanru@huawei.com>*
  - 陆璐[@Lulu_scut](https://gitcode.com/Lulu_scut), *<lul@scut.edu.cn>*
  - 龚思维[@gong-siwei](https://gitcode.com/gong-siwei), *<gongsiwei@huawei.com>*（[mstuner_catlass](https://gitcode.com/cann/catlass/blob/master/tools/tuner/README.md)工具**Committer**）

## 项目路标

- 2026Q1
  - 新增对下一代昇腾硬件平台的支持
  - 新增模板样例10+，包括W4A4量化算子模板样例
  - 新增资料文档10+，示例自定义算子开发和集成流程
  - 优化Tensor封装
- 2026Q2：
  - 新增Matmul样例10+，Conv样例5+，FA样例5+，展示不同功能特性的开发流程和优化技巧
  - 针对Matmul/GroupMamtul算子持续挖掘收益
  - 提供Trmm/Symm等更多优化示例

## TOP外部优秀贡献者

- 陆璐[@Lulu_scut](https://gitcode.com/Lulu_scut), *<lul@scut.edu.cn>*

## 社区运作

### 会议组织

- 双周例会，每双周周三 16:00-17:30 (北京时间)
  - 首次例会在`2025-10-29`举办，具体时间与调整可关注下方纪要与邮件列表
- 会议地址：[https://meeting.osinfra.cn/cann/](https://meeting.osinfra.cn/cann/)
- 议题申报&会议纪要：[https://etherpad-cann.meeting.osinfra.cn/p/sig-catlass](https://etherpad-cann.meeting.osinfra.cn/p/sig-catlass)

## SIG订阅

- 邮件列表：[https://mailweb.cann.osinfra.cn/mailman3/lists/catlass.cann.osinfra.cn/](https://mailweb.cann.osinfra.cn/mailman3/lists/catlass.cann.osinfra.cn/)
