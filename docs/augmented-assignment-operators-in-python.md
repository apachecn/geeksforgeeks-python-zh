# Python 中的扩充赋值运算符

> 原文:[https://www . geesforgeks . org/extended-assignment-operators-in-python/](https://www.geeksforgeeks.org/augmented-assignment-operators-in-python/)

赋值运算符是用于给变量赋值的运算符。像 Python 中的正常情况一样，我们编写“*a = 5*”*来为变量‘a’赋值 5。扩充赋值运算符在 Python 编程中有着特殊的作用。它基本上结合了算术或按位运算符和赋值运算符的功能。所以假设如果我们需要给变量“a”加 7，并将结果赋回“a”，那么我们可以使用增广赋值运算符，将表达式写成“ *a += 7* ”，而不是通常写成“ *a = a + 7* ”。这里+=结合了算术加法和赋值的功能。*

*因此，扩充赋值运算符提供了一种执行二进制运算并将结果赋回其中一个操作数的简单方法。写增广运算符的方法就是把二元运算符和赋值运算符写在一起。在 Python 中，我们有几种不同的增广赋值运算符，如+=、-=、*=、/=、/=、**=、|=、&=、> =、< < =、%=和^=.让我们借助一些示例代码来看看它们的功能:*

***1。加法和赋值(+=):** 这个运算符结合了算术加法和赋值的影响。在这里，*

> *T3] A = A+B can be written as a+= bT5]*

***例:***

 *## 蟒 3

```py
# Addition & Assignment
a = 15
b = 20

a += b
print(a)
```* ***输出**

```py
35
```

**2。减法和赋值(-=):** 这个运算符结合了减法和赋值的影响。

> T3] A = A–B can be written as a-= bT5]

**例:**

## 蟒 3

```py
# Subtraction & Assignment
a = 107
b = 99

a -= b
print(a)
```

**输出**

```py
8
```*