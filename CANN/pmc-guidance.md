

# pmc.yaml文件指导说明
***

## 简介
pmc.yaml 文件用于记录CANN组织中PMC成员信息。该文件位于community仓`CANN/PMC/pmc.yaml`目录下。

> 补充说明：pmc.yaml管理community仓库的PR合入权限（CANN/sigs下的具体SIG目录除外）。

## 关键角色配置
角色|	字段|	权限范围|
|------|----------|----------|
|PMC成员（PmcMember）|    pmc_members |		负责开源社区版本规划，开发状态跟踪，项目交付过程协调和版本发布会议召开等	|
|审批者（Committer）|	committers |	community仓库代码合并权限（可覆盖到文件级）|

##  pmc.yaml 文件格式

pmc.yaml 是 YAML 格式文件，包含以下顶层字段：
| 字段 | 类型 |层级| 说明 |
|--|--|--|--|
| name | 字符串 |一层| 项目名称，此处是CANN |
| description |  字符串 |一层| PMC描述信息 |
| pmc_members| 列表 | 一层|PMC对应的pmc_member名单 |
| repositories| 列表 |一层| PMC所管辖的仓库信息 |

其中 repositories 字段会说明PMC所管理的仓库的信息，repositories列表中的每一条记录可包含如下元素：
| 字段 | 类型 |层级| 说明 |
|--|--|--|--|
| repo| 列表|二层 | 仓库组，可以是一个仓库，也可以是一组仓库 ，可选|
| committers| 列表 |二层 | 仓库组对应的committer名单 ，可选|
| entry_configs | 列表 |二层 | 仓库下的目录或文件配置 ，可选|

上述entry_configs 列表中的每一条记录可包含如下元素：
| 字段 | 类型 | 层级|说明 |
|--|--|--|--|
| path | 列表 |-| 目录或者文件列表, 可选 |
| committers| 列表 |-| 目录或者文件列表下的committer名单, 可选 |

上述pmc_members、committers的每一条个人信息记录包含如下元素：
| 字段 | 类型 | 层级|说明 |
|--|--|--|--|
| gitcode_id | 字符串 |-| **GitCode ID**, 必填 |
| name | 字符串 |-| 姓名(或者网名), 可选 |
| email| 字符串 |-|  个人邮箱地址, 可选 |

## pmc.yaml 样例
```
# 组织/项目基本信息
name: CANN  # 组织/项目名称
description: 项目描述
pmc_members: 
  - gitcode_id: aaa
    name: aaa
    email: aaa@huawei.com
  - gitcode_id: bbb
    name: bbb
    email: bbb@huawei.com

repositories:                         #repositories 字段会说明PMC所管理的仓库组的信息
- repo:                               #仓库组，可以是一个仓库，也可以是一组仓库 ，可选字段
  - cann/community
  committers:                         #community仓库对应的committer名单 ，可选字段 （ccc和ddd拥有cann/community仓库下除了CANN目录的committer权限）
  - gitcode_id: ccc
  - gitcode_id: ddd
  entry_configs:                      #(repo)entry_configs字段会说明community仓库所管理的entry组的信息
  - path:                             #entry组，可以是一个目录或者完整的文件路径，也可以是一组目录或者完整的文件路径，可选字段
    - CANN
    committers:                       #entry组对应的committer名单 ，可选字段 （eee和fff拥有community仓库下CANN目录的committer权限）
    - gitcode_id: eee
    - gitcode_id: fff
```
