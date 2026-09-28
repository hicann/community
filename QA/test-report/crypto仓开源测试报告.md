# CANN/crypto 仓开源测试报告

## 1. 概述

本报告覆盖 CANN/crypto 仓已上仓的密码算子，包含 AES 工程的 AES-128-CTR、AES-128-GCM，以及 Keccak、SHAKE 工程的 KeccakF1600Tensor、Shake128Tensor、Shake256Tensor，对其功能、接口注册及计算精度进行验证。

AES 算子基于 CANN 8.5.2 验证功能与精度；Keccak、SHAKE 算子基于 CANN 9.1.0 验证算子构建出包、Host 单元测试、CPU 模拟 Kernel UT、ACLNN 调用、设备正确性及 SHAKE 重复运行稳定性。

本次范围为以下五个算子，不包含图模式适配和上层模型测试。

### 1.1 新增特性清单

| 序号 | 算子名称 | 所属工程 | 功能说明 |
| --- | --- | --- | --- |
| 1 | AES-128-CTR | `src/primitives/AES/` | AES-128 CTR 模式加密，使用 16 Byte Key、12 Byte Nonce |
| 2 | AES-128-GCM | `src/primitives/AES/` | AES-128 GCM 模式加密，输出 Ciphertext 与 16 Byte Authentication Tag，支持 AAD |
| 3 | KeccakF1600Tensor | `src/primitives/keccak/` | 对批量 1600 位状态执行 24 轮 Keccak-f[1600] 置换，输入、输出为 UINT32 / ND，形状为 `[50, B]` |
| 4 | Shake128Tensor | `src/algorithms/hash/shake/` | 对批量等长消息计算 SHAKE128，输入、输出为 UINT8 / ND，形状分别为 `[B, M]`、`[B, O]` |
| 5 | Shake256Tensor | `src/algorithms/hash/shake/` | 对批量等长消息计算 SHAKE256，输入、输出类型及布局与 Shake128Tensor 一致 |

SHAKE128、SHAKE256 共用一个 SHAKE 工程。SHAKE 构建包包含 KeccakF1600Tensor、Shake128Tensor、Shake256Tensor 三个算子，当前已提供的设备构建及调用日志来自该集成包。

### 1.2 测试活动

- 以 PyCryptodome 的 AES CTR、AES GCM 实现作为 CPU Reference，对 NPU 侧 AES 算子输出进行逐字节比对。
- 使用已安装 CANN 的算子 CMake 框架构建 Keccak、SHAKE 工程，验证包产物及 ACLNN 头文件、导出符号。
- 执行 Host 形状、Tiling、调度、参考实现、算术模型及构建脚本测试。
- 使用 GTest、tikicpulib 执行实际 Ascend C Kernel 的 CPU 模拟测试。
- 在 Atlas A2、Atlas A3 上执行 ACLNN 示例及逐字节设备正确性比较。
- 在两类设备上分别执行 100 轮 SHAKE 代表用例压力测试。

## 2. 版本测试信息

AES 算子与 Keccak、SHAKE 算子分别在不同 CANN 版本上完成验证，环境信息如下。

| 环境项 | AES 算子 | Keccak、SHAKE 算子（A2） | Keccak、SHAKE 算子（A3） |
| --- | --- | --- | --- |
| 产品型号 | A2/A3 | Atlas A2 | Atlas A3 |
| 设备编译目标 | NA | `ascend910b` | `ascend910_93` |
| 操作系统、CPU 架构 | x86/arm64 | ARM64（`aarch64`） | ARM64（`aarch64`） |
| CANN 版本 | 8.5.2 | 9.1.0 | 9.1.0 |
| Python 版本 | Python3.11 | 3.11.6 | 3.12.13 |
| CMake、C/C++ 编译器版本 | NA | CMake 3.27.9；C/C++：GCC 12.3.1 | CMake 3.27.9；C/C++：GCC 12.3.1 |

Keccak、SHAKE 算子的支持及验证范围为 CANN 9.1.0、Atlas A2 / Atlas A3。

Kernel UT 使用 GTest 1.11.0 和 CANN tikicpulib CPU 调试库，C++ ABI 为 `_GLIBCXX_USE_CXX11_ABI=0`。

CPU 模拟 Kernel UT 不调用实体 NPU，实际设备兼容性由各自的 ACLNN 设备测试验证。

## 3. 测试结论

基于 CANN 8.5.2 版本，共完成 AES-128-CTR 和 AES-128-GCM 两个算子的功能与精度测试，共执行 26 个测试用例，其中 AES-128-CTR 测试用例 21 个，AES-128-GCM 测试用例 5 个。AES-128-CTR 和 AES-128-GCM 算子功能正常，NPU 侧计算结果与 CPU Reference 结果一致，当前测试范围内未发现功能和精度问题，满足本次算子上仓的基本质量要求。

在 CANN 9.1.0 范围内，KeccakF1600Tensor、Shake128Tensor、Shake256Tensor 三个算子的已执行功能正确性测试通过，Atlas A2、Atlas A3 的构建出包、ACLNN 示例和设备正确性验证通过。SHAKE 在两类设备上分别完成 100 轮重复运行，结果均为 `STRESS_RESULT=100/100`。

Host 测试及 CPU 模拟 Kernel UT 通过。Kernel UT 每套配置包含 3 个测试程序、11 个参数化用例，结果均通过。

| 评估维度 | 测试结果 |
| --- | --- |
| 已交付算子数 | 5（AES 2 个，Keccak、SHAKE 3 个） |
| AES 功能与精度测试 | 通过，26 个测试用例，通过率 100% |
| A2 / A3 构建及 ACLNN 包符号检查 | 通过 |
| Host 单元及模型测试 | 通过 |
| CPU 模拟 Kernel UT | 两套运行记录均通过，每套 3 个程序、11 个用例 |
| A2 / A3 设备正确性 | 通过，每类设备 41 组参数用例 |
| A2 / A3 SHAKE 压力测试 | 通过，每类设备 100 轮 |

## 4. 特性质量评估

### 4.1 AES 算子 UT 测试

| 算子 | 测试内容 | 用例数 | 通过率 |
|---|---|---:|---:|
| AES-128-CTR | 算子注册、不同输入长度功能与精度验证 | 21 | 100% |
| AES-128-GCM | 算子注册、密文正确性、Tag正确性验证 | 5 | 100% |
| 总计 | - | 26 | 100% |

基于UT/ST验证上述全部测试用例，26 个测试用例均执行通过，通过率 100%。

### 4.2 AES-128-CTR 泛化及边界精度测试

AES-128-CTR 测试采用 PyCryptodome 提供的 AES CTR 实现作为 CPU Reference，并将 Ascend NPU 上 AES-128-CTR 算子的输出结果与 CPU Reference 结果进行逐字节比对。

CPU Reference 侧使用 16 Byte AES Key、12 Byte Nonce，并采用 CTR 模式生成期望密文。

测试覆盖以下输入长度：

| 类型 | 测试长度 |
|---|---|
| 小数据场景 | 1、15、16、17、64、128、256 Byte |
| 512 Byte边界场景 | 511、512、513 Byte |
| 1024 Byte边界场景 | 1023、1024、1025 Byte |
| 中等数据场景 | 2048、4096、8192 Byte |
| 大数据场景 | 10000、20000、50000、100000 Byte |

NPU 侧执行过程中，16 Byte AES Key 预先扩展为轮密钥，并转换为算子所需的 Tensor 格式，随后调用 AES-128-CTR 算子执行计算。

测试结果中，将 NPU 输出有效数据与 CPU Reference 结果进行比较，全部测试场景结果一致。

AES-128-CTR 精度测试通过率为 100%。

### 4.3 AES-128-GCM 泛化精度测试

AES-128-GCM 测试采用 PyCryptodome 提供的 AES GCM 实现作为 CPU Reference，同时对 NPU 输出的 Ciphertext 和 Authentication Tag 进行正确性验证。

CPU Reference 使用 16 Byte AES Key、12 Byte Nonce，并支持 Additional Authenticated Data（AAD）。

测试覆盖以下明文长度：

| 测试序号 | 明文长度 |
|---|---:|
| 1 | 20480 Byte |
| 2 | 40960 Byte |
| 3 | 61440 Byte |
| 4 | 737280 Byte |

每组测试均随机生成：

- 明文数据
- 16 Byte AES Key
- 12 Byte Nonce
- 32 Byte AAD

NPU 侧执行 AES-128-GCM 计算，并分别提取有效 Ciphertext 和 16 Byte Authentication Tag。

测试中分别比较：

1. NPU Ciphertext 与 CPU Reference Ciphertext
2. NPU Authentication Tag 与 CPU Reference Tag

两项结果均要求完全一致。

全部测试用例执行通过，AES-128-GCM 精度测试通过率为 100%。

### 4.4 AES 密钥扩展与预处理验证

AES-128-CTR 与 AES-128-GCM 测试共用 AES 密钥预处理模块。

测试辅助代码中定义 AES S-box、RCON，并通过 AES-128 Key Expansion 将 16 Byte Key 扩展为 11 轮 Round Key。

扩展后的 Round Key 转换为 Tensor，用于 NPU 算子输入。

本次测试中 CTR 和 GCM 算子均使用该预处理流程，相关功能测试均执行通过。

### 4.5 Keccak、SHAKE 构建出包与接口验证

| 测试环境 | 测试内容 | 结果 |
| --- | --- | --- |
| Atlas A2 + CANN 9.1.0 | 使用 `ascend910b` 构建 SHAKE 集成包，生成三个算子的 Kernel、Host Tiling、ACLNN 接口库与头文件 | 通过，`PACKAGE_SYMBOLS=PASS` |
| Atlas A3 + CANN 9.1.0 | 使用 `ascend910_93` 构建同一组算子 | 通过，`PACKAGE_SYMBOLS=PASS` |
| A2 设备调用 | SHAKE128 示例、SHAKE256 示例、设备正确性程序 | CTest 3/3 通过 |
| A3 设备调用 | SHAKE128 示例、SHAKE256 示例、设备正确性程序 | CTest 3/3 通过 |

安装目标将完整 vendor 包生成到构建目录，随后通过该包执行接口调用。

### 4.6 Keccak、SHAKE Host 单元测试与参考实现验证

| 测试范围 | 主要验证内容 | 结果 |
| --- | --- | --- |
| A2 云端 Host 测试 | Golden、生产 InferShape / Tiling、调度、参考实现、算术模型、构建脚本和 tiling 兼容检查 | 14/14 个 CTest 任务通过 |
| A3 云端 Host 测试 | 与 A2 相同范围的 Host 测试 | 14/14 个 CTest 任务通过 |
| 本地 SHAKE 工程回归 | 上述可在 Host 执行的测试；未启用可选 OpenSSL 差分项 | 13/13 个 CTest 任务通过 |
| 本地 Keccak 独立工程回归 | Golden、构建脚本、InferShape、Tiling、参考 KAT、置换模型、tiling 兼容 | 7/7 个 CTest 任务通过 |
| Keccak 置换算术模型 | 生产置换头与独立参考比较 | 928 个状态通过 |
| SHAKE Host 海绵模型 | 吸收、填充、置换、输出扩展，与 `hashlib` 比较 | 234 个参数组合通过 |
| SHAKE 纯 C 参考实现 | 编译后的纯 C 参考实现与 `hashlib` 比较 | 252 个参数组合通过 |

Keccak 参考实现与已知答案进行验证；SHAKE 纯 C 参考实现另经 `hashlib`、可选 OpenSSL 差分验证。参考实现仅用于测试，不链接到生产算子包。

Host 形状及 Tiling 测试覆盖非法尺寸、空指针、整数边界、工作组大小、分核数、tilingKey 和 workspace。构建脚本回归包含超时参数校验、GTest 编译链接检查及重新配置时的依赖检查。

不同运行环境可能启用不同的可选测试，多个任务内也包含参数化子项。

### 4.7 Keccak、SHAKE CPU 模拟 Kernel UT

通过 `ICPU_RUN_KF` 运行实际 Kernel，并与独立纯 C 参考逐元素或逐字节比较。

| 测试程序 | 内部用例数 | 代表输入 | A2 服务器 | A3 服务器 |
| --- | --- | --- | --- | --- |
| `keccak_kernel_ut` | 3 | batch = 64、256、320 | 通过 | 通过 |
| `shake128_kernel_ut` | 4 | `(B,M,O)` 为 `(1,0,1)`、`(17,65,33)`、`(33,169,169)`、`(65,337,339)` | 通过 | 通过 |
| `shake256_kernel_ut` | 4 | `(B,M,O)` 为 `(1,0,1)`、`(17,65,33)`、`(33,137,137)`、`(65,273,275)` | 通过 | 通过 |

每套运行共 3 个程序、11 个参数化用例，覆盖空消息、微块尾部、多块调度、跨 rate 吸收及多块输出。A2、A3 使用相同的测试程序及参数化用例。

| 测试程序 | A2 耗时（秒） | A3 耗时（秒） |
| --- | ---: | ---: |
| Keccak | 292.982 | 209.850 |
| SHAKE128 | 717.461 | 526.020 |
| SHAKE256 | 710.052 | 522.530 |
| 合计 | 1720.495 | 1258.400 |

A2、A3 的合计耗时均为三个测试程序耗时之和，统一保留三位小数。上述耗时仅记录 CPU 模拟测试执行时间。

### 4.8 Keccak、SHAKE 实际设备正确性与边界验证

使用 ACLNN 接口在真实设备上运行算子。Keccak 的期望结果由独立纯 C 参考实现生成；SHAKE 的期望结果由 OpenSSL EVP 生成。全部输出按字节严格比较。

| 算子 | 每类设备参数用例数 | 主要场景 | A2 | A3 |
| --- | ---: | --- | --- | --- |
| KeccakF1600Tensor | 5 | batch = 64、256、1024、4096、8192，随机状态置换 | 通过 | 通过 |
| Shake128Tensor | 18 | 空消息、小尺寸、微块与工作组边界、168 字节 rate 前后、多块吸收、多块输出 | 通过 | 通过 |
| Shake256Tensor | 18 | 空消息、小尺寸、微块与工作组边界、136 字节 rate 前后、多块吸收、多块输出 | 通过 | 通过 |
| 合计 | 41 | 按一次 batch / 输入长度 / 输出长度组合计一组参数用例 | 100% | 100% |

SHAKE 的 batch 覆盖 1、2、3、7、15、16、17、31、32、33、63、64、65、207、208、209、257、1024。输入、输出长度覆盖 rate 前后及两倍 rate 附近的边界。

A2、A3 各执行 41 组参数用例，共 82 组设备参数用例执行记录。

## 5. DFX专项质量评估

### 5.1 安全测试

本次未开展安全专项测试。

### 5.2 可靠性测试

AES 算子本次未开展可靠性专项测试。

SHAKE128、SHAKE256 在 A2、A3 上分别完成 100 轮压力测试，每轮 4 组参数用例，结果均为 `STRESS_RESULT=100/100`。

### 5.3 性能测试

本次未开展独立性能测试。4.7 节记录的耗时仅为 CPU 模拟 Kernel UT 的执行时间，不作为性能指标。

### 5.4 兼容性测试

AES 算子本次未开展兼容性专项测试。

Keccak、SHAKE 算子在 CANN 9.1.0 环境下，A2、A3 的算子构建、ACLNN 调用及设备正确性验证均通过。

## 6. 测试执行评估

### 6.1 测试覆盖

| 测试活动 | 测试结论 | 数量及统计口径 | 通过率 |
| --- | --- | --- | --- |
| AES-128-CTR 功能/精度测试 | pass | 21 个测试用例 | 100% |
| AES-128-GCM 功能/精度测试 | pass | 5 个测试用例 | 100% |
| AES 合计 | pass | 26 个测试用例 | 100% |
| A2 云端 Host 测试 | pass | 14 个 CTest 任务 | 100% |
| A3 云端 Host 测试 | pass | 14 个 CTest 任务 | 100% |
| A2 CPU 模拟 Kernel UT | pass | 3 个程序、11 个内部用例 | 100% |
| A3 CPU 模拟 Kernel UT | pass | 3 个程序、11 个内部用例 | 100% |
| A2 设备正确性 | pass | 41 组参数用例 | 100% |
| A3 设备正确性 | pass | 41 组参数用例 | 100% |
| A2 SHAKE 压力测试 | pass | 100 轮，每轮 4 组参数用例 | 100% |
| A3 SHAKE 压力测试 | pass | 100 轮，每轮 4 组参数用例 | 100% |
| 性能测试 | NA | NA | NA |
| 安全测试 | NA | NA | NA |

AES 测试重点覆盖 AES-128-CTR 和 AES-128-GCM 两个算子的接口注册、功能正确性、输入边界及结果精度验证。其中 AES-128-CTR 覆盖 20 种不同数据长度场景，AES-128-GCM 覆盖 4 种数据长度场景，并分别对 GCM 密文和 Authentication Tag 进行精度校验。

Keccak、SHAKE 测试覆盖构建出包与接口符号、Host 形状与 Tiling、CPU 模拟 Kernel 执行、真实设备逐字节正确性及重复运行稳定性。

## 7. 遗留问题和关键风险

不涉及。

## 8. 附件

不涉及。
