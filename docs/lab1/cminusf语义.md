# Cminusf 语义

> Cminusf 语法规则，可以参考 [Lab1 的介绍](../lab1/词法语法解析.md#cminusf-语法)

在语法规则中，我们定义了 Cminusf 语言的语法，接着，我们对照语法规则，给出相关的语义和解释。
在阅读前，需要理解 Cminusf 主要源自于 C 语言，因此它的行为都会接近 C 语言。

- $\text{program} \rightarrow \text{declaration-list}$
- $\text{declaration-list} \rightarrow \text{declaration-list}\ \text{declaration}\ |\ \text{declaration}$
- $\text{declaration} \rightarrow \text{var-declaration}\ |\ \text{fun-declaration}$

一个程序由一系列声明组成，声明包括了变量声明和函数声明，它们可以以任意顺序排列。

全局变量需要初始化为全 0。

所有的变量必须在使用前先进行声明，所有的函数必须在使用前先进行定义。

一个程序中至少要有一个 `main` 函数的声明。

因为没有原型这个概念，Cminusf 不区分函数的声明和定义。

- $\text{var-declaration}\ \rightarrow \text{type-specifier}\ \underline{\textbf{ID}}\ \underline{\textbf{;}}\ |\ \text{type-specifier}\ \underline{\textbf{ID}}\ \underline{\textbf{[}}\ \underline{\textbf{INTEGER}}\ \underline{\textbf{]}}\ \underline{\textbf{;}}$
- $\text{type-specifier} \rightarrow \underline{\textbf{int}}\ |\ \underline{\textbf{float}}\ |\ \underline{\textbf{void}}$

Cminusf 的基础类型只有整型 (`int`)、浮点型 (`float`) 和 `void`。而在变量声明中，只有整型和浮点型可以使用，`void` 仅用于函数声明。

一个变量声明定义一个整型或者浮点型的变量，或者一个整型或浮点型的数组变量（这里整型指的是 32 位有符号整型，浮点数是指 32 位浮点数）。

数组变量在声明时，$\textbf{INTEGER}$ 应当大于 0。

一次只能声明一个变量。

- $\text{fun-declaration} \rightarrow \text{type-specifier}\ \underline{\textbf{ID}}\ \underline{\textbf{(}}\ \text{params}\ \underline{\textbf{)}}\ \text{compound-stmt}$
- $\text{params} \rightarrow \text{param-list}\ |\ \underline{\textbf{void}}$
- $\text{param-list} \rightarrow \text{param-list}\ \underline{\textbf{,}}\ \text{param}\ |\ \text{param}$
- $\text{param} \rightarrow \text{type-specifier}\ \underline{\textbf{ID}}\ |\ \text{type-specifier}\ \underline{\textbf{ID}}\ \underline{\textbf{[}}\ \underline{\textbf{]}}$

函数声明包含了返回类型，标识符，由逗号分隔的形参列表，还有一个复合语句。

当函数的返回类型是 `void` 时，函数不返回任何值。

函数的参数可以是 `void` ，也可以是一个列表。当函数的形参是 `void` 时，调用该函数时不用传入任何参数。

形参中跟着中括号代表数组参数，它们可以有不同长度。

整型参数通过值来传入函数（pass by value），而数组参数通过引用来传入函数（pass by reference，即指针）。

函数的形参拥有和函数声明的复合语句相同的作用域，并且每次函数调用都会产生一组独立内存的参数（和 C 语言一致）。

函数可以递归调用。

- $\text{compound-stmt} \rightarrow \underline{\textbf{\{}}\ \text{local-declarations}\ \text{statement-list}\ \underline{\textbf{\}}}$

一个复合语句由一对大括号和其中的局部声明与语句列表组成。

复合语句的执行时，对包含着的语句按照语句列表中的顺序执行。

局部声明拥有和复合语句中的语句列表一样的作用域，且其优先级高于任何同名的全局声明（常见的静态作用域）。

- $\text{local-declarations} \rightarrow \text{local-declarations var-declaration}\ |\ \text{empty}$
- $\text{statement-list} \rightarrow \text{statement-list}\ \text{statement}\ |\ \text{empty}$

局部声明和语句列表都可以为空（empty 表示空字符串，即 $\varepsilon$）。

- $\begin{aligned}\text{statement} \rightarrow\ &\text{expression-stmt}\\\ &|\ \text{compound-stmt}\\\ &|\ \text{selection-stmt}\\\ &|\ \text{iteration-stmt}\\\ &|\ \text{return-stmt}\end{aligned}$
- $\text{expression-stmt} \rightarrow \text{expression}\ \underline{\textbf{;}}\ |\ \underline{\textbf{;}}$

表达式语句由一个可选的表达式（即可以没有表达式）和一个分号组成。

我们通常使用表达式语句中的表达式计算时产生的副作用，所以这种语句用于赋值和函数调用。

- $\begin{aligned}\text{selection-stmt} \rightarrow\ &\underline{\textbf{if}}\ \underline{\textbf{(}}\ \text{expression}\ \underline{\textbf{)}}\ \text{statement}\\\ &|\ \underline{\textbf{if}}\ \underline{\textbf{(}}\ \text{expression}\ \underline{\textbf{)}}\ \text{statement}\ \underline{\textbf{else}}\ \text{statement}\end{aligned}$

`if` 语句中的表达式将被求值，若结果的值等于 0，则第二个语句执行（如果存在的话），否则第一个语句会执行。

为了避免歧义，$\textbf{else}$ 将会匹配最近的 $\textbf{if}$。

- $\text{iteration-stmt} \rightarrow \underline{\textbf{while}}\ \underline{\textbf{(}}\ \text{expression}\ \underline{\textbf{)}}\ \text{statement}$

`while` 语句是 Cminusf 中唯一的迭代语句。它执行时，会不断对表达式进行求值，并且在对表达式的求值结果等于 0 前，循环执行下面的语句。

- $\text{return-stmt} \rightarrow \underline{\textbf{return}}\ \underline{\textbf{;}}\ |\ \underline{\textbf{return}}\ \text{expression}\ \underline{\textbf{;}}$

`return` 语句可以返回值，也可以不返回值。

未声明为 $\textbf{void}$ 类型的函数必须返回和函数返回类型相同的值。

`return` 会将程序的控制转移给当前函数的调用者，而 $\textbf{main}$ 函数的 `return` 会使得程序终止。

- $\text{expression} \rightarrow \text{var}\ \underline{\textbf{=}}\ \text{expression}\ |\ \text{simple-expression}$
- $\text{var} \rightarrow \underline{\textbf{ID}}\ |\ \underline{\textbf{ID}}\ \underline{\textbf{[}}\ \text{expression} \underline{\textbf{]}}$

一个表达式可以是一个变量引用（即 `var`）接着一个赋值符号（=）以及一个表达式，也可以是一个简单表达式。

`var` 可以是一个整型变量、浮点变量，或者一个取了下标的数组变量。

数组的下标值为整型，作为数组下标值的表达式计算结果可能需要类型转换变成整型值。

一个负的下标会导致程序终止，需要调用框架中的内置函数 `neg_idx_except`（该内部函数会主动退出程序，只需要调用该函数即可），但是对于上界并不做检查。

赋值语义为：先找到 `var` 代表的变量地址（如果是数组，需要先对下标表达式求值），然后对右侧的表达式进行求值，求值结果将在转换成变量类型后存储在先前找到的地址中。同时，存储在 `var` 中的值将作为赋值表达式的求值结果。

在 C 中，赋值对象（即 `var` ）必须是左值，而左值可以通过多种方式获得。Cminusf 中，唯一的左值就是通过 `var` 的语法得到的，因此 Cminusf 通过语法限制了 `var` 为左值，而不是像 C 中一样通过类型检查，这也是为什么 Cminusf 中不允许进行指针算数。

- $\text{simple-expression} \rightarrow \text{additive-expression}\ \text{relop}\ \text{additive-expression}\ |\ \text{additive-expression}$
- $\text{relop}\ \rightarrow \underline{\textbf{<=}}\ |\ \underline{\textbf{<}}\ |\ \underline{\textbf{>}}\ |\ \underline{\textbf{>=}}\ |\ \underline{\textbf{==}}\ |\ \underline{\textbf{!=}}$
- $\text{additive-expression} \rightarrow \text{additive-expression}\ \text{addop}\ \text{term}\ |\ \text{term}$
- $\text{addop} \rightarrow \underline{\textbf{+}}\ |\ \underline{\textbf{-}}$
- $\text{term} \rightarrow \text{term}\ \text{mulop}\ \text{factor}\ |\ \text{factor}$
- $\text{mulop} \rightarrow \underline{\textbf{*}}\ |\ \underline{\textbf{/}}$

一个简单表达式是一个加法表达式或者两个加法表达式的关系运算。当它是加法表达式时，它的值就是加法表达式的值。而当它是关系运算时，如果关系运算结果为真则值为整型值 1，反之则值为整型值 0。

加法表达式表现出了四则运算的结合性质与优先级顺序，四则运算的含义和 C 中的整型运算一致。

浮点数和整型一起运算时，整型值需要进行类型提升，转换成浮点数类型，且运算结果也是浮点数类型。

- $\text{factor} \rightarrow \underline{\textbf{(}}\ \text{expression}\ \underline{\textbf{)}}\ |\ \text{var}\ |\ \text{call}\ |\ \text{integer}\ |\ \text{float}$

因数可以是一个括号包围的表达式（此时它的值是表达式的值），或者是一个变量（此时它的值是变量的值），或者是一个函数调用（此时它的值是函数调用的返回值），或者是一个数字字面量（此时它的值为该字面量的值）。当因数是数组变量时，除非此时它被用作一个函数调用中的数组参数，否则它必须要带有下标。

- $\text{integer} \rightarrow \underline{\textbf{INTEGER}}$
- $\text{float} \rightarrow \underline{\textbf{FLOATPOINT}}$
- $\text{call} \rightarrow \underline{\textbf{ID}}\ \underline{\textbf{(}}\ \text{args} \underline{\textbf{)}}$
- $\text{args} \rightarrow \text{arg-list}\ |\ \text{empty}$
- $\text{arg-list} \rightarrow \text{arg-list}\ \underline{\textbf{,}}\ \text{expression}\ |\ \text{expression}$

函数调用由一个函数的标识符与一组括号包围的实参组成。实参可以为空，也可以是由逗号分隔的的表达式组成的列表，这些表达式代表着函数调用时，传给形参的值。函数调用时的实参数量和类型必须与函数声明中的形参一致，必要时需要进行类型转换。

Cminusf 中包含四个预定义的函数 `input` 、 `output`、 `outputFloat` 和 `neg_idx_except`，它们的声明为：

```c
int input(void) {...}
void output(int x) {...}
void outputFloat(float x) {...}
void neg_idx_except(void) {...}
```

- `input` 函数没有形参，且返回一个从标准输入中读到的整型值。
- `output` 函数接受一个整型参数，然后将它的值打印到标准输出，并输出换行符。
- `outputFloat` 函数接受一个浮点参数，然后将它的值打印到标准输出，并输出换行符。
- `neg_idx_except` 函数没有形参，执行后报错并退出。

除此之外，其它规则和 C 中类似，比如同一个作用域下不允许定义重名变量或函数。
