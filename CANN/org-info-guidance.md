# org-info.yaml文件指导说明
***

## 简介
org-info.yaml 文件用于记录CANN组织中各SIG的Maintainer信息。该文件位于community仓`CANN/org-info.yaml`目录下。

## 关键角色与权限
### SIG Maintainers (Special Interest Group Maintainers)
- 对应字段： sigs[].maintainers
- 权限范围：
	- 负责管理其所属 SIG 的 sig-info.yaml 文件。
	- 拥有该 SIG 名下所有仓库的一级（直接）Committer 权限。
- 角色说明： 由各 SIG 的核心维护者担任。

## 文件格式详解
org-info.yaml 是 YAML 格式文件，包含以下顶层字段：

| 字段 | 类型 |层级| 说明 |
|--|--|--|--|
| name | 字符串 |一层| 项目名称，此处是CANN |
| description |  字符串 |一层| 项目描述信息 |
| sigs| 列表 |一层| 项目组内所有sig的信息清单|

上述 sigs 的每一条个人信息记录包含如下元素：
| 字段 | 类型 | 层级|说明 |
|--|--|--|--|
| sig_name | 字符串 |二层|  sig组的名称, 必填 |
| maintainers | 列表 |二层| 项目看护者成员清单  |

上述 maintainers 的每一条个人信息记录包含如下元素：
| 字段 | 类型 | 层级|说明 |
|--|--|--|--|
| gitcode_id | 字符串 |三层|  **GitCode ID**, 必填 |
| name | 字符串 |三层| 姓名（或者网名）, 可选 |
| email| 字符串 |三层|  个人邮箱地址, 可选 |

## org-info.yaml 样例
```
# 组织/项目基本信息
name: CANN  # 组织/项目名称
description: 项目描述

# SIG 列表
sigs:
  # 第一个 SIG
  - sig_name: ops-basic  # SIG 名称 (必填)
    maintainers:  # 该 SIG 的 Maintainers
    - gitcode_id: ccc
      name: ccc
      email: ccc@huawei.com
    - gitcode_id: ddd
      name: ddd
      email: ddd@huawei.com

  # 第二个 SIG
  - sig_name: ops-transformer
    maintainers:
    - gitcode_id: ccc  # 同一个人可以在不同SIG担任Maintainer
      name: ccc
      email: ccc@huawei.com
    - gitcode_id: ddd
      name: ddd
      email: ddd@huawei.com
```