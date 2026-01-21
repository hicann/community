# ops-transformer SIG
算子transformer领域相关的兴趣小组，负责transformer相关融合算子，如FlashAttention、MoE（Mixture of Experts）等算子。

## 工作目标
- 1、负责transformer 算子领域技术路线规划和落地；
- 2、组织transformer 算子领域例会，引导技术讨论和决策；
- 3、负责周边组织沟通协调，推动落地相关项目；
- 4、负责SIG 仓库权限和邮件列表等基础设施的管理；
- 5、负责社区Bug、issue和邮件列表等渠道反馈的问题分发处理。

## 职责与范围
本SIG主要负责[ops-transformer](https://gitcode.com/cann/ops-transformer) 仓库的开发与维护：
- ops-transformer(transformer算子)
    - 定位：提供transformer相关常用算子
    - 功能：开发和管理以下类别的算子：
        - attention：对应各类attention 推理和训练算子
        - moe：对应MoE计算中，topk计算，合并MoE FFN的输出结果计算和routing计算等算子
        - gmm：对应实现分组矩阵乘计算等算子
        - mc2：对应通算并行算子和MOE 通信dispatch和combine算子
        - posembedding：对应旋转位置编码计算算子
        - ffn：对应MoeFFN和FFN等相关计算算子

## 组织会议：
两周一次例会，每单周周四上午10点-12点
- [会议链接](https://meeting.osinfra.cn/cann/)
- [会议议题&纪要](https://etherpad-cann.meeting.osinfra.cn/p/sig-ops-transformer)
- [邮件列表订阅](https://mailweb.cann.osinfra.cn/mailman3/lists/ops-transformer.cann.osinfra.cn/)

# 成员

### Maintainer列表
- 刘丹 [[@liudan12]](https://gitcode.com/liudan12)
- 俞郑中 [[@Allan_Yu]](https://gitcode.com/Allan_Yu)
- 黄俊健 [[@monologue815]](https://gitcode.com/monologue815)
- 马兵 [[@mabing1118]](https://gitcode.com/mabing1118)


### Committer列表
- 陈建军 [[@chenjianjun11]](https://gitcode.com/chenjianjun11)
- 杨彬榕 [[@yang-binrong]](https://gitcode.com/yang-binrong)
- 王民波 [[@wang-minbo]](https://gitcode.com/wang-minbo)
- 陈康 [[@chenkang30]](https://gitcode.com/chenkang30)
- 宋凯 [[@songkai111]](https://gitcode.com/songkai111)
- 高翔 [[@gaoxiang618]](https://gitcode.com/gaoxiang618)
- 黄伟 [[@huangwei791]](https://gitcode.com/huangwei791)
- 苗方正 [[@miaofangzheng]](https://gitcode.com/miaofangzheng)
- 温忻 [[@wenxin_fight]](https://gitcode.com/wenxin_fight)
- 王永光 [[@wangyongguang]](https://gitcode.com/wangyongguang)
- 於欣洁 [[@yu-xinjie62]](https://gitcode.com/yu-xinjie62)
- 刘博熙 [[@liuboxi]](https://gitcode.com/liuboxi)
- 唐超 [[@chaotang233]](https://gitcode.com/chaotang233)
- 胡碧霞 [@crystalhu](https://gitcode.com/crystalhu)
- 陈琳鑫 [@chen-linxin4](https://gitcode.com/chen-linxin4)

### 细分领域：
### moe committer列表：
- 宋凯 [@songkai111]
- 陈琳鑫 [@chen-linxin4]
- 於欣洁 [@yu-xinjie62]

### mc2 committer列表：
- 刘丹 [@liudan12]
- 陈建军 [@chenjianjun11]
- 王民波 [@wang-minbo]
- 刘博熙 [@liuboxi]

### ffn committer列表：
- 唐超 [@chaotang233]

### gmm committer列表：
- 陈康 [@chenkang30]
- 王永光 [@wangyongguang]
- 陈琳鑫 [@chen-linxin4]

### rope committer列表：
- 宋凯 [@songkai111]
- 於欣洁 [@yu-xinjie62] 
- 陈琳鑫 [@chen-linxin4]

### attention committer列表：
- 高翔 [@gaoxiang618]
- 黄伟 [@huangwei791]
- 苗方正 [@miaofangzheng]
- 杨彬榕 [@yang-binrong]
- 马兵 [@mabing1118]
- 胡碧霞 [@crystalhu]
- 於欣洁 [@yu-xinjie62] 


# 仓库清单

仓库地址：
- https://gitcode.com/cann/ops-transformer
