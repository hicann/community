# CANN 9.1.0-beta.3 测试报告
## 1. 概述

版本新增特性、修复问题请参考release-nodes：https://gitcode.com/cann/release-management/blob/master/9.1.0-beta.3/release-notes.md

## 2. 版本测试信息
**硬件和版本摘要**

*产品型号：Ascend 950PR、Atlas 900 A3 SuperPoD、Atlas 800T A2、Atlas 200T A2 Box16*

*操作系统：EulerOS 2.0 (SP12)、Ubuntu 24.04 LTS、OpenEuler22.03 LTS SP4*

*CANN版本：CANN 9.1.0-beta.3*

*驱动版本：Ascend HDK 26.0.RC1、Ascend HDK 25.5.2、Ascend HDK 25.5.1*



## 3. 测试结论

**本次社区发版本，共计执行3k+测试用例，未发现问题。无遗留问题，整体质量良好，满足出口质量标准。**


## 4. 特性质量评估
| 序号  | 子包                       |特性   |测试结论   |功能   |精度   |性能   |可靠性   |兼容性   |
|-----|--------------------------| ------------ | ------------ |------------   |------------   |------------   |------------   |------------   |
| 1   | cann-hccl                |Pass |Pass   |Pass   |Pass   |Pass   |Pass   |Pass   |
| 2   | cann-hixl                |Pass |Pass   |Pass   |Pass   |Pass   |Pass   |Pass   |
| 3   | cann-ops-math            |Pass |Pass   |Pass   |Pass   |Pass   |Pass   |Pass   |
| 4   | cann-ops-nn              |Pass |Pass   |Pass   |Pass   |Pass   |Pass   |Pass   |
| 5   | cann-ops-cv              |Pass |Pass   |Pass   |Pass   |Pass   |Pass   |Pass   |
| 6   | cann-ops-transformer     |Pass |Pass   |Pass   |Pass   |Pass   |Pass   |Pass   |
| 7 | ascend-transformer-boost |Pass |Pass   |Pass   |Pass   |Pass   |Pass   |Pass   |

## 5. DFX专项质量评估
### 5.1 1*24h 可靠性测试
本次测试覆盖各仓可靠性特性测试，及整包稳定性测试，符合版本出口稳定性要求。

| 序号  | 子包                       |可靠性特性   |测试结论   |遗留风险   |
|-----|--------------------------| ------------ | ------------ |------------   |
| 1   | cann-hccl                |Pass |Pass   |无 |
| 2   | cann-hixl                |Pass |Pass   |无 |
| 3   | cann-ops-math            |Pass |Pass   |无 |
| 4   | cann-ops-nn              |Pass |Pass   |无 |
| 5   | cann-ops-cv              |Pass |Pass   |无 |
| 6   | cann-ops-transformer     |Pass |Pass   |无 |
| 7 | ascend-transformer-boost |Pass |Pass   |无 |



### 5.2 性能测试


| 序号  | 子包                       | 性能指标  | 测试结论 | 遗留问题 |
|-----|--------------------------|-------|-----|-----|
| 1   | cann-hccl                | 性能无劣化 |Pass   |无 |
| 2   | cann-hixl                | 性能无劣化 |Pass   |无 |
| 3   | cann-ops-math            | 性能无劣化 |Pass   |无 |
| 4   | cann-ops-nn              | 性能无劣化 |Pass   |无 |
| 5   | cann-ops-cv              | 性能无劣化 |Pass   |无 |
| 6   | cann-ops-transformer     | 性能无劣化 |Pass   |无 |
| 7 | ascend-transformer-boost | 性能无劣化 |Pass   |无 |





### 5.3 兼容性测试
本次测试覆盖历史版本升级、各子包独立升级等兼容性测试，满足兼容性要求

| 序号  | 子包                       |验证结果   |遗留风险 |
|-----|--------------------------| ----------| -------|
| 1   | cann-hccl                |通过   |  无 |
| 2   | cann-hixl                |通过  |  无  |
| 3   | cann-ops-math            |通过   |  无  |
| 4   | cann-ops-nn              |通过   |  无  |
| 5   | cann-ops-cv              |通过  |  无  |
| 6   | cann-ops-transformer     |通过   | 无 |
| 7   | ascend-transformer-boost |通过   | 无   |




## 6. 测试执行评估

### 6.1 整包测试覆盖

### 6.1.1 冒烟测试

| 测试活动   |测试结论   |用例数   |用例覆盖率   |用例通过率
| ------------ | ------------ | ------------ |------------|------------|
|  算子 |pass   |351   | 100%   | 100% |
|  cann 多OS|pass |324  | 100%   | 100% |
|  atb |pass   |121   | 100%   | 100% |
|  HCCL |pass   |56   | 100%   | 100% |

### 6.1.2 长稳测试

| 测试活动   |测试结论   |用例数   |用例覆盖率   |用例通过率
| ------------ | ------------ | ------------ |------------|------------|
|  算子 |pass   |285   | 100%   | 100% |
|  cann 多OS|pass |440  | 100%   | 100% |
|  atb |pass   |1152   | 100%   | 100% |
|  HCCL |pass   |255   | 100%   | 100% |

### 6.1.3 基础测试项

| 测试活动   |测试结论   |用例数   |用例覆盖率   |用例通过率
| ------------ | ------------ | ------------ |------------|------------|
|  资料 |pass   |1   | 100%   | 100% |
|  Mindstudio基础功能|pass |360  | 100%   | 100% |
|  独立升级 |pass   |5   | 100%   | 100% |
|   需求测试 |pass   |不涉及, 无新需求合入   | 100%   | 100% |
|   合包测试 |pass   |4   | 100%   | 100% |



## 7. 遗留问题和关键风险

### 7.1  遗留问题和关键风险

无

## 8. 附件
不涉及