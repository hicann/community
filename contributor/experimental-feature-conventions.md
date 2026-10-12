# CANN社区试验特性规范

## 1. 总体原则

### 1.1 试验特性的定义

  试验特性（Experimental Feature）是指在软件或产品开发周期中，已完成初步开发、但尚未达到完全量产或全面商业化质量标准（如稳定性、兼容性或安全性）的产品功能。 这类功能可被下游试用与评估，但**不承诺向后兼容**，后续版本可能在不另行通知的情况下调整、重命名或移除。

 试验特性需遵循功能规划/方案设计与评审/开发/测试验证流程，常见的试验特性场景如下：

- **前沿技术探索**：引入处于孵化期或尚未完全成熟的前沿尖端技术，让用户抢先体验；
- **创新功能尝试**：快速提供创新功能特性，收集用户使用反馈；
- **基础重构平滑切换**：在需要更换底层架构或核心组件时，通过试验特性提供“新旧切换”开关，确保风险可控。

### 1.2 原则

应通过多种渠道让用户明确感知这些能力是试验性的、未来可能变更，以便提前评估迁移成本，包括但不限于：

- 资料（Release Notes、API Reference）；
- 代码注释（接口/参数等的注释块）；
- 编译期告警（C/C++）；
- IDE / 静态检查提示。

同时，应尽量减少试验特性正式商用时，需要用户修改的工作量，例如：

- 建议优先通过宏等机制集中管理试验标识，便于后续批量移除；
- 商用时仅移除标识宏，对外接口名称尽量保持不变。

---

## 2. 资料与文档要求

试验特性在资料侧应满足以下要求：

- **Release Notes**：新增 / 变更 / 下线的试验特性须在`版本说明`中列出，并标注 `试验特性`。
- **API Reference**：试验性接口、参数、类、结构体、枚举、宏、变量、常量须在`API参考手册`中标注 `试验`说明。
- **README / 示例代码**：使用试验特性的示例须在文件开头或代码注释中明确声明，避免被用户直接复制到生产代码。

## 3. C / C++语言试验特性

### 3.1 组件定义公共的试验特性宏

建议组件定义公共的试验特性宏，命名格式： `<组件名>_EXPERIMENTAL`，GCC/Clang 用 `__attribute__((warning))`、MSVC 用 `__declspec(deprecated)` 触发编译告警，本组件下的试验接口都引用该特性宏，便于后续批量替换与移除。例如：RTS 组件使用 `RTS_EXPERIMENTAL`，AMCT 组件使用 `AMCT_EXPERIMENTAL`。

参考：

```cpp
#ifndef RTS_EXPERIMENTAL
  #if defined(__GNUC__) || defined(__clang__)
    #define RTS_EXPERIMENTAL \
        __attribute__((warning("This is experimental and may change without notice.")))
  #elif defined(_MSC_VER)
   /* MSVC 无原生 warning 属性，使用 deprecated 替代但消息中增加not deprecated说明*/
    #define RTS_EXPERIMENTAL \
        __declspec(deprecated("This is experimental and may change without notice, not deprecated."))
  #else
    /* 未知编译器，避免构建失败 */
    #define RTS_EXPERIMENTAL
  #endif
#endif
```

说明：`<组件名>_EXPERIMENTAL`适用于试验接口，可以根据需求自行增加宏参数；

### 3.2 试验性接口

**目的**：对外开放的接口尚未稳定，标记为试验性，用户调用时需要编译告警 。

**规范**：

1. 在接口声明前增加试验说明，编译时触发告警，建议参考3.1定义`<组件名>_EXPERIMENTAL`组件共用。
2. 在接口上方写 `Warning` 注释块，说明试验性质与可能的变更。

参考（C++举例）：

```cpp
/* 接口声明前加 <组件名>_EXPERIMENTAL */
/*
 * Warning: This save_ptd is experimental and may change without notice.
 * API接口描述
 */
RTS_EXPERIMENTAL runtime::Error save_ptd();

//用户以下场景会告警
err1 = save_ptd();     // 编译时告警 ✅
```

### 3.3 函数试验性参数

**目的**：函数本身稳定，但个别参数尚在试验阶段，需要有注释提示。

**规范**：

1. 在接口注释中增加 `Warning` 注释块，说明该参数为试验性与可能的变更。

参考（C++举例）：

```cpp
/*
 * Warning: This `enable_ai_denoise` parameter is experimental and may change without notice.
 */
void InitializeAudioHardware(int audio_config, bool enable_ai_denoise = false);
```

### 3.4 试验性类 / 结构体 / 枚举

**目的**：整个 class /struct /  enum 尚未稳定，需要有注释提示。

**规范**：

1. class/ struct / enum 增加 `Warning` 注释块，说明试验性质与可能的变更。

参考（C++举例）：

```cpp
// 试验类
/* 
 * Warning: This class TransducerRunner is experimental and may change without notice.
 * class 描述 XXXX
 */
class TransducerRunner {
};
```

```cpp
// 试验结构体
/*
 * Warning: This struct RawAudio is experimental and may change without notice.
 * struct 描述 XXXX
 */
struct RawAudio {};
```

```cpp
// 试验枚举
/*
 * Warning: This enum RawAudioFormat is experimental and may change without notice.
 * enum 描述 XXXX
 */
enum class RawAudioFormat {
    PCM_16,
    PCM_24,
    FLOAT_32
};
```

### 3.5 试验性类成员变量 / 结构体成员变量 / 枚举项

**目的**：class /struct的个别成员变量 或 enum的个别枚举项 尚未稳定，需要有注释提示。

**规范**：

1. class /struct /enum 增加 `Warning` 注释块，说明成员变量或枚举项的试验性质与可能的变更。

参考（C++举例）：

```cpp
/*
 * Warning: This class's ptr member is experimental and may change without notice.
 */
class TransducerRunner {
    int *ptr;            // 类的试验成员变量
};

/*
 * Warning: This struct's raw member is experimental and may change without notice.
 */
struct RawAudio {
    int *raw;            // 结构体试验成员变量
};

/*
 * Warning: This enum's INTRI_VAR is experimental and may change without notice.
 */
enum class IntriType {
    INTRI_VAR = 1 // 试验枚举项
};
```

### 3.6 试验性常量 / 变量 

**目的**：常量 / 变量 尚未稳定，需要有注释提示。

**规范**：

1. 增加 `Warning` 注释块，说明试验性质与可能的变更。

参考（C++举例）：

```cpp
// 试验性常量
/*
 * Warning: This MAX_THROUGHPUT is experimental and may change without notice.
 * 试验性全局常量说明
 */
const int MAX_THROUGHPUT = 9430; 

// 试验性变量
/*
 * Warning: This g_connection_count is experimental and may change without notice.
 * 试验性变量说明
 */
int g_connection_count = 0;
```

### 3.7 试验性宏定义

**目的**：宏尚未稳定，需要有注释提示。

**规范**：

1. 增加 `Warning` 注释块，说明试验性质与可能的变更。

参考（C++举例）：

```cpp
/*
 * Warning: This MAX_RETRY_EXP is experimental and may change without notice.
 * 试验性宏说明
 */
#define MAX_RETRY_EXP 100
```

## 4. Python 语言试验特性

### 4.1 试验性接口

**目的**：对外开放的接口尚未稳定，标记为试验性。

**规范**：

1. 在接口注释中增加 `Warning` 注释块，说明试验性质与可能的变更。

参考：

```python
def calculate_optimal_route(start: str, end: str) -> list:
    """
    Warning: This calculate_optimal_route is experimental and may change without notice.
    API接口说明
    """
    ...
```

### 4.2 函数试验性参数

**目的**：函数本身稳定，但个别参数尚在试验阶段，需要有注释提示。

**规范**：

1. 在接口注释中增加 `Warning` 注释块，说明该参数为试验性与可能的变更。

参考：

```python
def render_video(video_path: str, gpu_accelerate: bool = False) -> None:
    """
    Warning: This `gpu_accelerate` parameter is experimental and may change without notice.
    API接口说明
    """
    ...
```

### 4.3 试验性类 / 类的试验性成员

**目的**：整个类或类个别成员变量尚未稳定，需要有注释提示。

**规范**：

1. 在注释中增加 `Warning` 注释块，说明类或成员变量为试验性与可能的变更。

参考：

```python
class BetaDatabase:
    """
    Warning: This class BetaDatabase is experimental and may change without notice.
    class说明
    """
    def __init__(self):
        self.status = "connected"

class AppConfig:
    """
    Warning: This class's beta_cache member is experimental and may change without notice.
    class说明
    """
    def __init__(self):
        self.host = "127.0.0.1"          # 正常变量
        self.beta_cache = True           # 试验性变量    
```

### 4.4 试验性枚举 / 枚举的试验性成员

**目的**：整个枚举或个别枚举成员尚未稳定，需要有注释提示。

**规范**：

1. 在注释中增加 `Warning` 注释块，说明枚举或枚举成员为试验性与可能的变更。

参考：

```python
from enum import Enum
# 整个枚举为试验性
class FeatureGate(Enum):
    """
    Warning: This enum FeatureGate is experimental and may change without notice.
    enum说明
    """
    V3_COMPILER = "v3_compiler"
    WEB_BLOCKCHAIN = "web_blockchain"

# 仅部分成员为试验性
class SystemMode(Enum):
    STANDARD = "standard"                # 正常成员
    
    # Warning: This enum's AI_AUTO_PILOT is experimental and may change without notice.
    AI_AUTO_PILOT = "ai_auto_pilot"      # 试验性成员
```

### 4.5 试验性变量/常量

**目的**：变量 / 常量 尚未稳定，需要有注释提示。

**规范**：

1. 在注释中增加 `Warning` 注释块，说明变量或常量为试验性与可能的变更。

参考：

```python
# Warning: _cache_size is experimental and may change without notice.
_cache_size = 100   # 变量初始化

# Warning: CONSTANT is experimental and may change without notice.
CONSTANT = 100   # 常量初始化
```

## 5. 试验特性兼容性与生命周期

**兼容性**：试验特性不保证向后兼容。

**试验特性生命周期/稳定化流程**：试验 → 评估 → GA（移除标记）/ 废弃

```
试验特性生命周期：
  1）试验期（Experimental）  打标记、可变更、不承诺向后兼容
  2）评估期                  收集反馈，形态趋于稳定。
  3）GA                     正式商用，移除试验标记，发布迁移指引，承诺按版本兼容策略进行维护。
  4）废弃（可选）            转为废弃（deprecated），发布废弃声明，给出移除时间表。
```

## 6. 附则

本指南由 CANN 社区负责维护与更新，修订需经评审通过后生效。

社区成员对指南内容有疑问或建议，可通过官方渠道反馈。