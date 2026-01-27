# tsc.yaml文件指导说明
***

## 简介
tsc.yaml 文件用于记录CANN组织中TSC成员信息。该文件位于community仓`CANN/TSC/tsc.yaml`目录下。

## 关键角色与权限
### TSC Member （TSC-Technical Steering Committee）
- 对应字段： tsc_members
- 定位与职责：
    - 定义CANN项目的技术发展方向和愿景，决策重大技术事项；
    - 制定、修改技术指导委员会相关制度；
    - 选举、任免技术指导委员会主席及委员;
    - 决策孵化新项目并成立对应PMC，撤销项目和审议PMC委员的变动等；
    - 决策SIG（Special Interest Group 特别兴趣小组）的成立和撤销；
    - 其他对社区有重要影响的技术工作。
## 文件格式详解
tsc.yaml 是 YAML 格式文件，包含以下顶层字段：

| 字段 | 类型 |层级| 说明 |
|--|--|--|--|
| name | 字符串 |一层| 项目名称，此处是CANN |
| description |  字符串 |一层| 项目描述信息 |
| tsc_members| 列表 | 一层|TSC对应的tsc_member名单 |

上述tsc_members的每一条个人信息记录包含如下元素：
| 字段 | 类型 | 层级|说明 |
|--|--|--|--|
| gitcode_id | 字符串 |-| **GitCode ID**, 必填 |
| name | 字符串 |-| 姓名(或者网名), 可选 |
| email| 字符串 |-|  个人邮箱地址, 可选 |

## tsc.yaml 样例
```
# 组织/项目基本信息
name: CANN  # 组织/项目名称
description: 项目描述
tsc_members: 
  - gitcode_id: aaa
    name: aaa
    email: aaa@huawei.com
  - gitcode_id: bbb
    name: bbb
    email: bbb@huawei.com

```