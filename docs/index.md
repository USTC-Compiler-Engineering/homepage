# 编译工程

!!! Info "说明"

    本课程主页为 2025 秋季学期徐伟、李诚老师班《编译工程》课程主页。

<hr class="hr-my" data-content="(●′∀｀●) 我是分隔线 (●′∀｀●)">

## 课程简介

本课程重点围绕编译器优化设计，强调适用于当代计算机（多核及嵌入式处理器）的代码生成与优化技术的一般原理和基本实现方法。本课程包括编译器概述、代码生成、并行编译器与依赖性分析、机器无关优化、指令级并行编译、并行性与局部性优化等。本课程将借助开源的编译器基础设施软件，让学生实习有关的优化设计技术。

## 课程信息

### 上课时间与地点

    时间：2~16 周，4(3,4,5)
    地点：高新校区 GT-B103

### 联系方式

教师

- 主讲教师：李诚 （<chengli7@ustc.edu.cn>）
- 主讲教师：徐伟 （<xuweihf@ustc.edu.cn>）

助教

- 肖同欢（<tonghuanxiao@mail.ustc.edu.cn>）
- 王宇航（）

其它

## 公告

- 暂无

## 教学课件

|    日期    |                              标题                               |                                                                                                                                  课件                                                                                                                                  |
| :--------: | :-------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
<!--
| 2025-02-27 |                       编译原理和技术导论                        |                                                                                                                [Lecture1_Intro](ppt/Lecture1-Intro.pdf)                                                                                                                |
| 2025-02-27 |                            词法分析                             |                                                                                                         [Lexical-analysis](ppt/Lecture2-Lexical-analysis.pdf)                                                                                                          |
| 2025-03-06 |                            语法分析                             |                                       [Parser-part1](ppt/Lecture3-Parser-part1.pdf), [Parser-part2](ppt/Lecture4-Parser-part2.pdf), [Parser-part3](ppt/Lecture5-Parser-part3.pdf), [Parser-part4](ppt/Lecture6-Parser-part4.pdf)                                       |
| 2025-03-13 |                            语法分析                             |                                                              [Parser-part5](ppt/Lecture7-Parser-part5.pdf), [Parser-part6](ppt/Lecture8-Parser-part6.pdf), [Parser-part7](ppt/Lecture9-Parser-part7.pdf)                                                               |
| 2025-03-20 |                  实验 - 语言解析器与IR自动生成                  |                                                                                          [Lab1-Part1](ppt/Lecture10-lab-part1.pdf), [Lab1-Part2](ppt/Lecture10-lab-part2.pdf)                                                                                          |
| 2025-03-27 |                   中间代码表示，中间代码生成                    |                    [IR](ppt/Lecture11-IR.pdf), [IR-Translation-part1](ppt/Lecture12-IR%20Translation-part1.pdf), [IR-Translation-part2](ppt/Lecture13-IR%20Translation-part2.pdf), [IR-Translation-part3](ppt/Lecture14-IR%20Translation-part3.pdf)                    |
| 2025-04-03 |                          中间代码生成                           | [IR-Translation-part4](ppt/Lecture15-IR%20Translation-part4.pdf), [IR-Translation-part5](ppt/Lecture16-IR%20Translation-part5.pdf), [IR-Translation-part6](ppt/Lecture17-IR%20Translation-part6.pdf), [IR-Translation-part7](ppt/Lecture18-IR%20Translation-part7.pdf) |
| 2025-04-10 |                  实验-IR自动生成 & 运行时环境                   |               [Lab2-part1](ppt/Lecture19-lab-part1.pdf), [Lab2-part2](ppt/Lecture19-lab-part2.pdf), [Runtime-part1](ppt/Lecture20-Runtime-part1.pdf), [Runtime-part2](ppt/Lecture20-Runtime-part2.pdf), [Runtime-part3](ppt/Lecture20-Runtime-part3.pdf)               |
| 2025-04-17 |                    机器无关代码优化&龙芯汇编                    |                                                                                           [IR-opt-part1](ppt/Lecture21-IR-opt-part1.pdf), [LA-asm](ppt/Lecture21-LA-asm.pdf)                                                                                           |
| 2025-04-24 |                        机器无关代码优化                         |                                                     [IR-opt-part1](ppt/Lecture24-IR%20Opt-part1-v2.pdf), [IR-opt-part2](ppt/Lecture25-IR%20Opt-part2-v2.pdf), [IR-opt-part3](ppt/Lecture26-IR%20Opt-part3-v2.pdf)                                                      |
| 2025-05-08 |                        机器无关代码优化                         |                                                                                                      [IR-opt-part4](ppt/Lecture27-IR%20Opt-part4-Mem2Reg.pdf), [IR-opt-part5](ppt/Lecture28-IR%20Opt-part5-v2.pdf)                                                                                                      |
|                           2025-05-29                            |                                     后端代码生成与优化   | [CodeSel](ppt/Lecture29-CodeSel.pdf), [RegAlloc-part1](ppt/Lecture30-RegAlloc-part1.pdf), [RegAlloc-part2](ppt/Lecture31-RegAlloc-part2.pdf), [phi](ppt/Lecture32-phi函数接合.pdf) |
-->
<!--    | 2024-10-16 |     语法制导翻译 - 语法制导翻译方案 & L 属性定义的翻译方案      |                                                                           [Translation-part2](ppt/Lecture12-Translation-part2.pdf), [Translation-part3](ppt/Lecture13-Translation-part3.pdf)                                                                           |
| 2024-10-21 |               语法制导翻译 - L 属性定义的翻译方案               |                                                                                                        [Translation-part4](ppt/Lecture14-Translation-part4.pdf)                                                                                                        |
| 2024-10-23 |      中间代码翻译 - 简单语句翻译 & 控制流与布尔表达式翻译       |                                                                   [IR-Translation-part1](ppt/Lecture15-IR%20Translation-part1.pdf), [IR-Translation-part2](ppt/Lecture16-IR%20Translation-part2.pdf)                                                                   |
| 2024-10-28 |             中间代码翻译 - 布尔表达式 & 控制流语句              |                                                                   [IR-Translation-part3](ppt/Lecture17-IR%20Translation-part3.pdf), [IR-Translation-part4](ppt/Lecture18-IR%20Translation-part4.pdf)                                                                   |
| 2024-10-30 |               中间代码翻译 - 类型表达式及自动构造               |                                                                                                    [IR-Translation-part5](ppt/Lecture19-IR%20Translation-part5.pdf)                                                                                                    |
| 2024-11-04 |          中间代码翻译 - 类型表达式 & 符号表与声明语句           |                                                                                                    [IR-Translation-part6](ppt/Lecture20-IR%20Translation-part6.pdf)                                                                                                    |
| 2024-11-06 |         中间代码翻译 - 数组寻址 & 运行时管理 - 存储组织         |                                                                           [IR-Translation-part7](ppt/Lecture21-IR%20Translation-part7.pdf), [Runtime-part1](ppt/Lecture22-Runtime-part1.pdf)                                                                           |
| 2024-11-11 |                      运行时管理 - 栈式分配                      |                                                                                   [Runtime-part2](ppt/Lecture23-Runtime-part2.pdf), [Runtime-part3](ppt/Lecture24-Runtime-part3.pdf)                                                                                   |
| 2024-11-13 |                     代码生成 - 简单机器模型                     |                                                                                                            [CodeGen-part1](ppt/Lecture25-CodeGen-part1.pdf)                                                                                                            |
| 2024-11-18 |                 机器无关代码优化 - 常见优化方法                 |                                                                                                            [IR Opt-part1](ppt/Lecture26-IR%20Opt-part1.pdf)                                                                                                            |
| 2024-11-20 |             机器无关代码优化 - 数据流与到达定值分析             |                                                                                                            [IR Opt-part2](ppt/Lecture27-IR%20Opt-part2.pdf)                                                                                                            |
| 2024-11-25 | 机器无关代码优化 - 可用表达式分析 & 活跃变量分析 & 基本块内优化 |                                                          [IR Opt-part3](ppt/Lecture28-IR%20Opt-part3.pdf), [IR Opt-part4](ppt/Lecture29-IR%20Opt-part4.pdf), [IR Opt-part5](ppt/Lecture30-IR%20Opt-part5.pdf)                                                          |
| 2024-11-27 |                    流图中的循环 & 寄存器分配                    |                                                                                              [Loop](ppt/Lecture31-Loop-part1.pdf), [Register](ppt/Lecture32-Register.pdf)                                                                                              | -->                                                                                                                |

<!--| 2024-11-29 |                          面向目标机器的代码优化                           |                                                                              [part1](https://rec.ustc.edu.cn/share/d6169380-9045-11ee-8a37-87201671ab8d)                                                                              |
| 2024-12-04 |                               guest lecture                               |                                                                                                               无 slides                                                                                                               |
| 2024-12-06 |                               guest lecture                               |                                                                                                               无 slides                                                                                                               |
| 2024-12-13 |                                  复习课                                   |                                                                             [slides](https://rec.ustc.edu.cn/share/3a4ffcf0-995a-11ee-9fdc-a7ee4ffd604e)                                                                              | -->

## 参考资料

### 教材和参考书

- <div id='textbook'></div> 陈意云、张昱，编译原理（第 3 版），高等教育出版社，2014
- A. V. Aho, M. S. Lam, R. Sethi, and J. D. Ullman 著，赵建华等译，编译原理，机械工业出版社，2017

### 其他资料

- Stanford 课程主页：[http://web.stanford.edu/class/cs143/](http://web.stanford.edu/class/cs143/)
- MIT 课程主页：[http://6.035.scripts.mit.edu/fa18/](http://6.035.scripts.mit.edu/fa18/)

## 如何使用本文档？

### 关于提示框

为了便于标识，我们在文档中提供了若干提示框。它们有着不同的形式与作用。例如：

!!! Note "一般的提示框长这样"

    里面是这样的文字。

??? Question "有的提示框默认是折叠的，需要点击才能展开"

    然后看到里面的内容。

???+ Success "有的提示框则是默认展开的"

    如果觉得碍事可以点击折叠。

!!! Example "大家可以在后续的文档中接触到它们。"

### 关于搜索

你可以在右上角搜索框中输入想要查询的关键词，文档会给出对应的查询结果与跳转链接。

???+ Note "Tips"

    如果在阅读文档时发现有自己不清楚的知识点，可以先用搜索框查询其是否在先前的文档中出现过。

<!-- <hr class="hr-my" data-content="(●′∀｀●) 我是分隔线 (●′∀｀●)">


???+ Bug "评论系统"

    由于主页上的评论系统映射可能出现问题，以防万一，我们在这里进行一些补充。

    除了上面介绍的内容，本学期的实验文档我们还额外添加了评论系统。大家可以在各个界面下方找到类似的评论栏，登录自己的 GitHub 账号即可发表相应的评论。

    <strong>怎么使用？</strong>

    评论系统的输入采用 Markdown 格式。如果你之前没有用过 Markdown，可以简单地将其当做普通文本（txt）格式，直接输入文字并点击评论即可。如果你对 Markdown 语法有所了解，可以使用 **加粗**、 *斜体* 、句内的 `code block` 等特殊格式，以及相应的标题结构。

    除了留下自己的疑问，大家也可以解答其他同学的疑问。这是一个相互交流、相互合作的平台。我们鼓励合理范围内的讨论与思考~

    <strong>其他方式</strong>

    评论系统实际上是抓取了[这个仓库](https://github.com/USTC-Compiler-2024/Compiler-Comments)下讨论区的内容，所有的评论也会发布在这里。大家可以访问上面的仓库进行阅读。

    如果你没有或者无法登录 GitHub 账号也没关系。除了文档下方的评论系统，在课程群中大家也可以提出自己的问题，我们将统一进行解答。

    欢迎大家在评论系统里畅所欲言！ -->
