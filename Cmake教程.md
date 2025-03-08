# `Cmake`教程

### **基本概念：**

- **Makefile**：
   是一个文本文件，用来定义项目的构建过程，通常包括编译源代码文件、链接对象文件、清理文件等规则。`Makefile` 是一个基于命令行的工具，通过 `make` 命令来执行构建过程。
- **CMake**：
   是一个跨平台的构建工具，它生成适合特定平台的构建文件（例如 `Makefile`、`Ninja` 文件、Visual Studio 项目文件等）。`Cmake`本身并不直接执行构建过程，而是生成目标平台所需的构建脚本或项目文件。`CMakeLists.txt` 是 `Cmake`的配置文件，里面定义了构建的规则。

先编写`Cmake`文件然后执行`Cmake`后生成makefile文件，makefile文件才是自动进行编译链接的自动脚本

一般 C/C++ 项目都会遵循这样的目录结构：

```
/my_project
 ├── src/         # 存放源文件 (.c/.cpp)
 │   ├── main.c
 │   ├── module1.c
 │   ├── module2.c
 │
 ├── include/     # 存放头文件 (.h)
 │   ├── module1.h
 │   ├── module2.h
 │
 ├── CMakeLists.txt  # CMake 配置文件
 ├── build/       # 编译输出目录（CMake 生成）
 ├── bin/         # 可执行文件存放目录
 ├── lib/         # 生成的库文件（.a/.so）
 ├── docs/        # 文档
 ├── tests/       # 测试代码
```

### 📌 **常见文件夹用途**

| 文件夹     | 用途                                        |
| ---------- | ------------------------------------------- |
| `src/`     | 存放 `.c/.cpp` 源文件                       |
| `include/` | 存放 `.h` 头文件（公共 API）                |
| `build/`   | CMake 生成的编译目录（可以 `gitignore` 掉） |
| `bin/`     | 存放编译后的可执行文件                      |
| `lib/`     | 存放生成的静态库 `.a` 或动态库 `.so`        |
| `docs/`    | 项目文档                                    |
| `tests/`   | 测试代码（单元测试等）                      |

------

### 📌 **CMake 配置文件示例（自动匹配 src/ 和 include/）**

```
cmake_minimum_required(VERSION 3.10)
project(MyProject)

set(CMAKE_C_STANDARD 99)

# 自动查找 src/ 目录下的所有 C 文件
file(GLOB SOURCES "src/*.c")

# 设置 include 目录，供编译器查找头文件
include_directories(include)

# 生成可执行文件
add_executable(my_program ${SOURCES})
```

这样，CMake 就会：

1. **自动找到 `src/` 里的 `.c` 文件**
2. **自动找到 `include/` 里的 `.h` 头文件**
3. **编译并生成 `my_program`**