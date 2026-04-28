# Ops-solver仓开源演练测试报告
## 1. 概述
<span style="color:rgb(33,149,243)">*本报告基于ops-solver开源仓提供能力，验证快速搭建开发环境、执行算子实现编译、算子功能测试*</span>

## 2. 版本测试信息

<span style="color:rgb(33,149,243)">*产品型号：A2/A3*</span>

<span style="color:rgb(33,149,243)">*操作系统：x86/arm64*</span>

<span style="color:rgb(33,149,243)">*CANN版本：8.5.RC1*</span>

<span style="color:rgb(33,149,243)">*Python版本：Python3.8*</span>

## 3. 测试结论

<span style="color:rgb(33,149,243)">*基于8.5.0和9.0.0版本，共计执行 10 个测试用例，遗留问题均已闭环。整体质量良好，满足出口质量标准。*</span>


## 4. 特性质量评估

<span style="color:rgb(30,136,229)">*新特性的验证结果清单。*</span>

|序号   | 特性          |测试结论   |功能   | 精度 | 性能 | 可靠性 | 兼容性 |
| ------------ |-------------| ------------ |------------   |----|----|-----|-----|
|   1| ops-solver仓 |通过   |Pass   | NA | NA | NA  | NA  |

## 5. DFX专项质量评估
### 5.1 安全测试
<span style="color:rgb(30,136,229)">*本次演练不涉及*</span>

### 5.2 可靠性测试
<span style="color:rgb(30,136,229)">*该仓不涉及*</span>

### 5.3 性能测试

<span style="color:rgb(30,136,229)">*该仓不涉及*</span>


### 5.4 兼容性测试
<span style="color:rgb(30,136,229)">*本次演练不涉及*</span>

## 6. 测试执行评估

### 6.1 测试覆盖
<span style="color:rgb(30,136,229)">*特性以及关键测试活动的测试覆盖情况*</span>

| 测试活动   | 测试结论 | 用例数 | 用例通过率 |
|--------|------|-----|-------|
| 特性测试   | pass | 9   | 100%  |
| 资料测试   | pass | 1   | 100%  |
| 可靠性测试  | NA   | NA  | NA    |
| 继承特性测试 | NA   | NA  | NA    |
| 兼容性测试  | NA   | NA  | NA    |
| 安全测试   | NA   | NA  | NA    |


## 7. 遗留问题和关键风险
1、贡献指南/安全声明/许可证跳转为空
2、缺少UT测试能力
3、从开始的README.md到《从开发一个简单算子出发.md》中间无跳转，存在断点
4、《从开发一个简单算子出发.md》中测试脚本的运行结果示例内容相对实际执行，实际执行中打屏信息太多，无法跟结果快速匹配
5、CANN版本安装部分为什么选取的是产品线出的社区版本，而不是开源仓社区版本？
6、初始README.md中使能环境变量指令和test目录下的README.md中使能环境变量命令不一致
7、ops-solver/test/cgetrf/README.md 中样例执行命令错误bash build.sh --op=cgetrf --run     应为--ops;cgetri、sgetrf、sgetri test目录的README.md存在相同问题
8、cgetrf在A2形态执行test用例结果失败
9、test目录下的cgetrf/cgetri/sgetrf/sgetri 的README.md中“算子约束：。无。 ” 前后两个圈看着怪怪的，容易误以为排版问题

除遗留问题2已纳入Q2需求外，其余问题均已解决。


## 8. 附件
不涉及
