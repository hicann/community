# ops-nn SIG
## 概述
ops-nn SIG是神经网络相关算子研发兴趣小组，负责如矩阵乘、卷积、激活等神经网络常用算子。 

## 工作目标
- 1、负责神经网络算子领域技术路线规划和落地；
- 2、组织神经网络算子领域例会，引导技术讨论和决策；
- 3、负责周边组织沟通协调，推动落地相关项目；
- 4、负责SIG 仓库权限和邮件列表等基础设施的管理；
- 5、负责社区Bug、issue和邮件列表等渠道反馈的问题分发处理。

## 职责与范围
本SIG主要负责[ops-nn](https://gitcode.com/cann/ops-nn) 仓库的开发与维护：
- ops-nn(神经网络算子)
    - 定位：提供神经网络计算常用算子
    - 功能：开发和管理以下类别的算子：
        - activation（激活类）：提供如relu、gelu等激活类算子
        - control（控制流类）：提供如条件分支、循环等流程控制能力算子，如assert算子
        - conv（卷积类）：提供conv2d等卷积操作类算子
        - foreach（循环操作类）：提供如foreach_abs、foreach_add等遍历计算算子
        - index（索引操作类）：提供index_fill、scatter等索引操作类算子
        - loss（损失函数类）：提供l1_loss、mse_loss等loss计算类算子
        - matmul（矩阵乘类）：提供matmul、batchmatmul等矩阵乘计算类算子
        - norm（归一化类）：提供layer_nrom、batch_norm等数据归一化计算算子
        - optim（优化器类）：提供adamw等优化器类算子
        - pooling（池化类）：提供avgpool、maxpool等池化计算类算子 
        - quant（量化操作类）：提供quant、dequant等量化计算类算子 
        - rnn（循环神经网络类）：提供rnn计算算子
        - vfusion（融合操作类）：提供vector融合计算类算子

## 边界与协作
为保持清晰的职责划分，ops-nn SIG与社区其他算子兴趣小组紧密协作，但专注于上述核心领域。 本SIG与[ops-basic SIG](../ops-basic/README.md)和[ops-transformer SIG](../ops-transformer/README.md)共同提供深度学习网络服务。本SIG负责ops-nn仓，其中在CANN架构中位置如下图所示：
![alt text](image.png)


# 成员

### Maintainer列表
- 唐玮玮[@tangweiwei2](https://gitcode.com/tangweiwei2), *tangweiwei2@huawei.com*
- 陈琦[@chenqi317](https://gitcode.com/chenqi317), *chenqi317@huawei.com*
- 刘波[@liubo75](https://gitcode.com/liubo75), *liubo75@huawei.com*
- 胡碧霞[@crystalhu](https://gitcode.com/crystalhu), *hubixia1@huawei.com*

### Committer列表
- 周奇龙[@zhou-qilong](https://gitcode.com/zhou-qilong), *zhouqilong2@huawei.com*
- 范其瑞[@fanqirui](https://gitcode.com/fanqirui), *fanqirui1@huawei.com*
- 郑李磊[@lileizheng](https://gitcode.com/lileizheng), *zhenglilei@huawei.com*
- 刘伟[@liu-wei](https://gitcode.com/liu-wei), *lovline.liuwei@huawei.com*
- 王永光[@wangyongguang](https://gitcode.com/wangyongguan), *wangyongguang1@huawei.com*
- 於欣洁[@yu-xinjie62](https://gitcode.com/yu-xinjie62), *yuxinjie1@huawei.com*
- 唐超[@chaotang233](https://gitcode.com/chaotang233), *tangchao47@huawei.com*
- 查建青[@zhajianqing123](https://gitcode.com/zhajianqing123), *zhajianqing@huawei.com*
- 唐燕峰[@FelixTang7](https://gitcode.com/FelixTang7), *tangyanfeng@huawei.com*
- 张瑜翔[@zhangyuxiang0119](https://gitcode.com/zhangyuxiang0119), *zhangyuxiang21@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*

### 细分领域：
### foreach、activation、norm、quant committer列表：
- 王永光[@wangyongguang](https://gitcode.com/wangyongguan), *wangyongguang1@huawei.com*
- 周奇龙[@zhou-qilong](https://gitcode.com/zhou-qilong), *zhouqilong2@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*
- 查建青[@zhajianqing123](https://gitcode.com/zhajianqing123), *zhajianqing@huawei.com*

### control committer列表：
- 刘伟[@liu-wei](https://gitcode.com/liu-wei), *lovline.liuwei@huawei.com*
- 唐燕峰[@FelixTang7](https://gitcode.com/FelixTang7), *tangyanfeng@huawei.com*
- 查建青[@zhajianqing123](https://gitcode.com/zhajianqing123), *zhajianqing@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*

### index、hash committer列表：
- 周奇龙[@zhou-qilong](https://gitcode.com/zhou-qilong), *zhouqilong2@huawei.com*
- 王永光[@wangyongguang](https://gitcode.com/wangyongguan), *wangyongguang1@huawei.com*
- 唐燕峰[@FelixTang7](https://gitcode.com/FelixTang7), *tangyanfeng@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*

### vfusion、loss、optim committer列表：
- 周奇龙[@zhou-qilong](https://gitcode.com/zhou-qilong), *zhouqilong2@huawei.com*
- 王永光[@wangyongguang](https://gitcode.com/wangyongguan), *wangyongguang1@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*
- 於欣洁[@yu-xinjie62](https://gitcode.com/yu-xinjie62), *yuxinjie1@huawei.com*

### rnn、pooling committer列表：
- 王永光[@wangyongguang](https://gitcode.com/wangyongguan), *wangyongguang1@huawei.com*
- 周奇龙[@zhou-qilong](https://gitcode.com/zhou-qilong), *zhouqilong2@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*
- 张瑜翔[@zhangyuxiang0119](https://gitcode.com/zhangyuxiang0119), *zhangyuxiang21@huawei.com*

### matmul committer列表：
- 范其瑞[@fanqirui](https://gitcode.com/fanqirui), *fanqirui1@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*
- 唐超[@chaotang233](https://gitcode.com/chaotang233), *tangchao47@huawei.com*

### conv committer列表：
- 郑李磊[@lileizheng](https://gitcode.com/lileizheng), *zhenglilei@huawei.com*
- 章武[@zhang-wu](https://gitcode.com/zhang-wu), *zhangwu3@huawei.com*
- 张瑜翔[@zhangyuxiang0119](https://gitcode.com/zhangyuxiang0119), *zhangyuxiang21@huawei.com*

# 社区运作

### 会议组织

- 公开的会议时间：北京时间，两周一次例会，单周(每月第一、第三周)周五下午14:00-16:00

### 会议纪要

- [会议地址](https://meeting.osinfra.cn/cann/)
- [会议纪要](https://etherpad-cann.meeting.osinfra.cn/p/sig-ops-nn)

### 贡献指南
- [贡献指南](https://gitcode.com/cann/ops-nn/blob/master/CONTRIBUTING.md)

# SIG订阅

- [邮件订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/ops-nn.cann.osinfra.cn/)

# 仓库清单

仓库地址：
- https://gitcode.com/cann/ops-nn