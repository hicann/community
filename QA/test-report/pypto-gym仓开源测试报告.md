# pypto-gym仓开源演练测试报告
## 1. 概述
本报告基于pypto-gym开源仓提供能力，验证快速搭建开发环境、执行算子与模型测试。

## 2. 版本测试信息

- 产品型号：A2/A3
- 操作系统：x86/arm64
- CANN版本：9.1.0
- Python版本：Python3.13

## 3. 测试结论

基于9.1.0版本，共计执行4项测试任务，覆盖82个算子和10个模型场景，遗留问题均已闭环。整体质量良好，满足出口质量标准。

## 4. 特性质量评估

### 4.1 全量算子UT/ST测试

| 模型/场景 |算子数量 | 通过率 |
|-------|--------|--------|
| qwen3_next | 1 | 100% |
| minimax_m27 | 1 | 100% |
| chunked_gdr | 1 | 100% |
| glm_v4_5 | 7 | 100% |
| deepseek_v4 | 7 | 100% |
| llada2_moe | 2 | 100% |
| deepseek_v32_exp | 6 | 100% |
| spatial_ssrl_3b | 2 | 100% |
| qat | 1 | 100% |
| deepseek_v2_lite_chat | 1 | 100% |
| qwen3_6_27b | 1 | 100% |
| qwen3_5_9b | 1 | 100% |
| arctic | 1 | 100% |
| phi_3_mini_4k_instruct | 1 | 100% |
| qwen3_1_7b | 1 | 100% |
| gutenocr_3b | 2 | 100% |
| gemma4_31b | 2 | 100% |
| experimental | 44 | 100% |
| 总计 | 82 | 100% |

基于UT/ST验证代码仓全量82个算子，通过率100%。

### 4.2 全量模型测试

|模型 | 融合组件 | 验证结果 |
|-------|--------|--------|
|qwen3_1_7b | rms norm + rope | 通过 |
|phi_3_mini_4k_instruct | mla | 通过 |
|qwen3_vl_8b_instruct_unredacted_max | GQA | 通过 |
|spatial_ssrl_3b | rope + rms norm | 通过 |
|gutenocr_3b | rope + rms norm | 通过 |
|qwen3_5_9b | GDR | 通过 |
|gemma4_31b_it | Softmax, GQA | 通过 |
|llada2_moe | Grouped GEMM | 通过 |
|qwen3_6_27b | GDR | 通过 |
|deepseek_v2_lite_chat | mla | 通过 |

验证代码仓全量10个模型样例，通过率100%。

### 4.3 主要算子泛化精度测试

| 场景 |算子数量 | case数量 | 通过率 |
|-------|--------|--------|--------|
| DeepSeek | 6 | 5863 | 100% |
| GLM | 8 | 4163 | 100% |
| Operator | 7 | 582 | 100% |
| GreenLight | 13 | 1315 | 100% |
| 总计 | 34 | 11923 | 100% |

选取34个高优先级算子参与泛化验证，通过率100%。

### 4.4 主要算子性能测试

|算子名 | 场景数量 | ASC/AICore | ASC/Prof | 
|-------|--------|--------|--------|
|inplace_add_rmsnorm | 4 | 0.54 | 0.46 | 
|mla_prolog_v3 | 2 | 0.75 | 0.68 | 
|mla_prolog_v3_quant | 2 | 0.66 | 0.59 | 
|interleave_rope | 4 | 0.69 | 0.5 | 
|sparse_flash_attn_antiquant | 4 | 0.69 | 0.63 | 
|sparse_flash_attn | 4 | 0.82 | 0.73 | 
|glm_attention | 4 | 0.58 | 0.52 | 
|flash_attention_mha | 2 | 0.6 | 0.26 | 
|flash_attention_mha_grad | 2 | 0.42 | 0.27 | 
|mhc_post | 2 | 0.6 | 0.32 | 
|apply_adam | 2 | 0.77 | 0.73 | 
|incre_flash_attention_mla | 4 | 0.53 | 0.51 | 
|平均 | - | 0.64 | 0.52 | 

选取12个Top算子，构造低时延、高吞吐、预训练和后训练等场景case进行验证，基于泳道图的平均性能为0.64倍AscendC算子，基于profiling的平均性能为0.52倍AscendC算子，符合预期。


## 5. DFX专项质量评估
### 5.1 安全测试
本次演练不涉及

### 5.2 可靠性测试
该仓不涉及

### 5.3 性能测试
该仓不涉及

### 5.4 兼容性测试
本次演练不涉及

## 6. 测试执行评估

### 6.1 测试覆盖
特性以及关键测试活动的测试覆盖情况

| 测试活动   | 测试结论 | 用例数 | 用例通过率 |
|--------|------|-----|-------|
| 特性测试   | pass | 82   | 100%  |
| 资料测试   | pass | 1   | 100%  |
| 可靠性测试  | NA   | NA  | NA    |
| 继承特性测试 | NA   | NA  | NA    |
| 兼容性测试  | NA   | NA  | NA    |
| 安全测试   | NA   | NA  | NA    |


## 7. 遗留问题和关键风险
不涉及

## 9. 附件
不涉及