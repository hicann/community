# CANN社区组织管理 

## 一、创建SIG组
新建SIG需要向技术指导委员会提交新建SIG申请，议题经技术指导委员会审批通过后，SIG发起人需要完成SIG各类权限配置。

### 如何向技术委员会提交新建SIG申请
#### 确认SIG符合申请条件
申请之前请确保该SIG符合[SIG治理章程](https://gitcode.com/cann/community/blob/master/governance/sig-governance.md)。
#### 提交申请
向技术委员会（TSC）提交新建SIG申请，需要在技术委员会（TSC）例会申报议题，申报议题方式有两种：
1. 订阅[技术委员会邮箱](https://mailweb.cann.osinfra.cn/mailman3/lists/tsc.cann.osinfra.cn/)，收到例会通知后，直接回复会议邮件，申报会议议题（例：`1. XXX SIG新建申请 -- 申请人：XXX`）。
2. 直接在技术委员会（TSC）[会议纪要模板](https://etherpad.meeting.osinfra.cn/p/TSC)进行申报，将相关议题和申报人员信息等刷新到对应例会议题中（例：`1. XXX SIG新建申请 -- 申请人：XXX`）。
> 申请模板详见[SIG组申报模板](https://gitcode.com/cann/community/blob/master/templates/SIG%E7%BB%84%E7%94%B3%E6%8A%A5%E6%A8%A1%E6%9D%BF%20v0.1.pptx)。
### 权限配置
#### SIG代码仓管理权限
 SIG 发起人需修改 CANN/community 仓库, 配置maintainer, committer名单。

#### 第一步：修改组织架构

（1）Fork 并修改：Fork CANN/community 仓库，修改 org-info.yaml（[org-info.yaml编写指南](https://gitcode.com/cann/community/blob/master/CANN/org-info-guidance.md)），新增该 SIG 组的定义。

（2）提交 PR：提交 PR 至 master 分支（pr描述中需要附加评审纪要）；

（3）✅通过审查并合入pr：此 PR 需获得 cann-cla/yes, lgtm, approved 三个标签，需由tsc_members评论 /lgtm和/approve后自动合入。
- cann-cla/yes：CLA协议检查。机器人会自动检查您commits中的邮箱是否已签署CLA协议。若已签署，将添加此标签；若未签署，会添加cann-cla/no标签并留言提示;
- lgtm：请联系org-info.yaml中tsc_members进行评审。评审通过后，由 maintainer评论/lgtm;
- approved：联系tsc_members进行批准。批准后，由tsc_members评论 /approve。

#### 第二步：创建SIG目录和committer信息文件

（1）在第一个PR合并后，在相应项目的 sigs 目录下创建新的 SIG 组目录；
创建信息文件：在该目录中创建 sig-info.yaml 文件([sig-info.yaml编写指南](https://gitcode.com/cann/community/blob/master/CANN/sig-info-guidance.md))，并配置 maintainers、committers 等信息；

（2）提交 PR：提交第二个 PR 至 master 分支（pr描述中需要附加评审纪要）；

（3）✅通过审查并合入pr：此 PR 需获得 cann-cla/yes, lgtm, approved 三个标签后自动合入：
- cann-cla/yes：CLA协议检查。机器人会自动检查您commits中的邮箱是否已签署CLA协议。若已签署，将添加此标签；若未签署，会添加cann-cla/no标签并留言提示;
- lgtm：请联系org-info.yaml中该SIG组的maintainers进行评审。评审通过后，由 maintainer评论/lgtm;
- approved：联系该SIG组的maintainers进行批准。批准后，由maintainer评论 /approve。

（4）PR合入后，您需要登录[社区会议平台](https://meeting.osinfra.cn/cann)的个人中心将gitcode账号与华为账号绑定，绑定GitCode ID后，CANN社区SIG maintainer、committer自动拥有创建会议权限。具体会议指导详见[会议指南](https://gitcode.com/cann/infrastructure/blob/main/docs/meeting/CANN%E7%A4%BE%E5%8C%BA%E4%BC%9A%E8%AE%AE%E6%8C%87%E5%8D%97.md)。
+ 注意：<font color="red">权限每隔1小时刷新一次，配置后请耐心等待</font>
 
（5）PR合入后，如果该SIG组需要新建邮件列表，需要maintainer在新建sig的community的Gitcode的PR里[@weixin_43493709](https://gitcode.com/weixin_43493709)，并描述："你好，需要新建邮件列表，邮件列表名为xxx@cann.osinfra.cn"（其中xxx代表sig名）。



## 二、SIG组变更(任免 maintainer committer)
### 变更流程
任免 maintainer committer流程详见[SIG治理章程](https://gitcode.com/cann/community/blob/master/governance/sig-governance.md)。

### 权限配置

#### 情况一：maintainer任免

1.  Fork 并修改：Fork `CANN/community` 仓库到您的个人账号，修改 `org-info.yaml` （[org-info.yaml编写指南](https://gitcode.com/cann/community/blob/master/CANN/org-info-guidance.md)）和SIGREADME.md里面人员信息。
2.  提交 PR：向 `CANN/community` 仓库的 `master` 分支提交 PR
3.  ✅  通过审查并合入pr：您的 PR 需要获得以下三个标签才能被合并：

    - `cann-cla/yes`：**CLA协议检查**。机器人会自动检查您 commits 中的邮箱是否已签署 CLA 协议。若已签署，将添加此标签；若未签署，会添加 `cann-cla/no` 标签并留言提示
    - `lgtm`：请联系 `org-info.yaml` 文件中列出的 **tsc_members** 进行评审。评审通过后，由tsc_member 评论 `/lgtm`，机器人会自动添加标签
    - `approved`：同样联系 **tsc_members** 进行批准。批准后，由tsc_member 评论 `/approve`，机器人会自动添加标签

#### 情况二：committer任免
1.  Fork 并修改：Fork `CANN/community` 仓库，修改目标 SIG 的 `sig-info.yaml` 文件([sig-info.yaml编写指南](https://gitcode.com/cann/community/blob/master/CANN/sig-info-guidance.md))和SIG README.md里面人员信息。
2.  提交 PR：向 `CANN/community` 仓库的 `master` 分支提交 PR
3.  ✅  通过审查并合入pr：您的 PR 需要获得以下三个标签才能被合并：
    - `cann-cla/yes`：**CLA协议检查**。机器人会自动检查您 commits 中的邮箱是否已签署 CLA 协议。若已签署，将添加此标签；若未签署，会添加 `cann-cla/no` 标签并留言提示
    - `lgtm`：请联系 `org-info.yaml` 中该 SIG 组的 **maintainers** 进行评审。评审通过后，由 maintainer 评论 `/lgtm`
    - `approved`：同样联系该 SIG 组的 **maintainers** 进行批准。批准后，由 maintainer 评论 `/approve`


## 三、SIG组终止
### 变更流程
终止SIG流程详见[SIG治理章程](https://gitcode.com/cann/community/blob/master/governance/sig-governance.md)。

### 权限配置

#### 第一步：移除SIG目录

（1）在第一个PR合并后，在相应项目的 sigs 目录下删除对应SIG组目录；

（2）提交 PR：提交第二个 PR 至 master 分支（pr描述中需要附加评审纪要）；

（3）✅通过审查并合入pr：此 PR 需获得 cann-cla/yes, lgtm, approved 三个标签后自动合入：
- cann-cla/yes：CLA协议检查。机器人会自动检查您commits中的邮箱是否已签署CLA协议。若已签署，将添加此标签；若未签署，会添加cann-cla/no标签并留言提示;
- lgtm：请联系org-info.yaml中该SIG组的maintainers进行评审。评审通过后，由 maintainer评论/lgtm;
- approved：联系该SIG组的maintainers进行批准。批准后，由maintainer评论 /approve。

（4）PR合入后，SIG组成员在SIG组对应的会议预定权限、代码合入权限等会被取消。

#### 第二步：修改组织架构

（1）Fork 并修改：Fork CANN/community 仓库，修改 org-info.yaml（[org-info.yaml编写指南](https://gitcode.com/cann/community/blob/master/CANN/org-info-guidance.md)），删除该 SIG 组的定义。

（2）提交 PR：提交 PR 至 master 分支（pr描述中需要附加评审纪要）；

（3）✅通过审查并合入pr：此 PR 需获得 cann-cla/yes, lgtm, approved 三个标签，需由tsc_members评论 /lgtm和/approve后自动合入。
- cann-cla/yes：CLA协议检查。机器人会自动检查您commits中的邮箱是否已签署CLA协议。若已签署，将添加此标签；若未签署，会添加cann-cla/no标签并留言提示;
- lgtm：请联系org-info.yaml中tsc_members进行评审。评审通过后，由 maintainer评论/lgtm;
- approved：联系tsc_members进行批准。批准后，由tsc_members评论 /approve。

## 四、PMC成员变更
### 变更流程
PMC变更流程详见[PMC治理章程](https://gitcode.com/cann/community/blob/master/governance/pmc-governance.md)。

### 权限配置
1.  Fork 并修改：Fork `CANN/community` 仓库到您的个人账号，修改 `CANN/pmc.yaml` 。
2.  提交 PR：向 `CANN/community` 仓库的 `master` 分支提交 PR
3.  ✅  通过审查并合入pr：您的 PR 需要获得以下三个标签才能被合并：

    - `cann-cla/yes`：**CLA协议检查**。机器人会自动检查您 commits 中的邮箱是否已签署 CLA 协议。若已签署，将添加此标签；若未签署，会添加 `cann-cla/no` 标签并留言提示
    - `lgtm`：请联系 `pmc.yaml` 文件中列出的 **pmc_members** 进行评审。评审通过后，pmc_member 评论 `/lgtm`，机器人会自动添加标签
    - `approved`：同样联系 **pmc_members** 进行批准。批准后，由pmc_members评论 `/approve`，机器人会自动添加标签



## 五、TSC成员变更
### 变更流程
TSC变更流程详见[TSC治理章程](https://gitcode.com/cann/community/blob/master/governance/tsc-governance.md)。

### 权限配置
1.  Fork 并修改：Fork `CANN/community` 仓库到您的个人账号，修改 `CANN/tsc.yaml` 。
2.  提交 PR：向 `CANN/community` 仓库的 `master` 分支提交 PR
3.  ✅  通过审查并合入pr：您的 PR 需要获得以下三个标签才能被合并：

    - `cann-cla/yes`：**CLA协议检查**。机器人会自动检查您 commits 中的邮箱是否已签署 CLA 协议。若已签署，将添加此标签；若未签署，会添加 `cann-cla/no` 标签并留言提示
    - `lgtm`：请联系 `tsc.yaml` 文件中列出的 **tsc_members** 进行评审。评审通过后，tsc_member 评论 `/lgtm`，机器人会自动添加标签
    - `approved`：同样联系 **tsc_members** 进行批准。批准后，由tsc_members评论 `/approve`，机器人会自动添加标签