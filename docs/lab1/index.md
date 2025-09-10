

# Lab1 中间代码生成

本次实验需要同学们在助教提供的 Cminusf 解析器基础上，完成从语法树向中间代码的自动化翻译过程。

!!! warning "Deadline"

    本次实验的截止日期为 2025-04-20 23:59:59

## 实验准备

请克隆 [Lab1 仓库](https://github.com/USTC-Compiler-2025/2025ustc-compiler.git)

??? note "ZLIB 相关报错"

    如果你在 `cmake ..` 一步遇到如下报错`Target "IR_lib" links to target "ZLIB::ZLIB" but the target was not found.`，请使用 `sudo apt install zlib1g-dev` 安装 zlib 库，然后重新 `cmake .. && make`。


## 实验内容

- 内容一：
  阅读 [AST](./AST.md), [Light IR 手册](./LightIR.md) 和 [LightIR C++ 库](./LightIR C++.md)，掌握抽象语法树节点定义 Light IR，使用 Light IR C++ 库生成 IR 的方法。
- 内容二：
  阅读[访问者模式](./visitor_pattern.md)，理解 C++ 访问者模式的工作原理及遍历顺序。

阅读 [IR 自动化生成](./autogen.md)，[Cminusf 语义](./cminusf语义.md)，补充 `include/cminusfc/cminusf_builder.hpp` 与 `src/cminusfc/cminusf_builder.cpp` 文件，并通过 `tests/2-ir-gen/autogen/testcases/` 目录下所有提供的测试样例。

## 提交内容

提交你的代码仓库链接至助教邮箱即可
