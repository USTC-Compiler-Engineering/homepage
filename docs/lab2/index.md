# Lab2

接下来，我们将让大家体验如何通过增加优化 pass 让生成的代码快起来。正如课上所讲，优化的方法有很多，由于时间关系，我们不能一一尝试。因此，我们为大家准备了三个优化Pass：死代码删除、常量传播、函数内联。

!!! warning "Deadline"

    本次实验的截止日期为 2025-06-08 23:59:59

## 同步实验仓库

在进行实验之前，首先拉取实验仓库的最新代码。

本次实验仓库更新的内容如下，每个阶段的文件将在对应文档详细说明：

```
.
├── ...
├── include
│   ├── ...
│   └── passes
│       ├── DeadCode.hpp            # 死代码删除
│       ├── Dominators.hpp          # 支配树分析
│       ├── FuncInfo.hpp            # 纯函数分析
│       ├── Mem2Reg.hpp             # Mem2Reg 分析
│       ├── FuncInline.hpp          # 函数内联
│       ├── ConstPropagation.hpp    # 常量传播
│       └── PassManager.hpp         # PassManager：管理 pass 的运行
├── src
│   ├── ...
│   └── passes
│       ├── ...
│       ├── Dominators.cpp        
│       ├── FuncInline.cpp        
│       ├── ConstPropagation.cpp  
│       └── Mem2Reg.cpp
└── tests
    ├── ...
    └── 2-ir-gen                   # 本地测试
```

## 实验内容

请至少完成 **死代码删除** 优化Pass，在此基础上可以尝试常量传播、函数内联或其他优化Pass。

Pass管理在main.cpp中，如果想添加或修改优化Pass顺序，可以自行修改。

死代码删除和常量传播 Pass 可以参考 [PPT](../ppt/Lecture24-IR%20Opt-part1-v2.pdf)，函数内联 Pass 可以参考[这篇文章](https://zhuanlan.zhihu.com/p/395552440)。

## 提交方式

请提交仓库链接至助教邮箱
