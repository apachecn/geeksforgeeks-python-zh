# 蟒 3 入门

> 原文:[https://www.geeksforgeeks.org/introduction-to-python3/](https://www.geeksforgeeks.org/introduction-to-python3/)

Python 是一种高级通用编程语言。Python 程序通常比 Java 等其他编程语言小。程序员必须键入相对较少的内容，语言的缩进要求使它们始终可读。

**注意:**更多信息请参考 [Python 编程语言](https://www.geeksforgeeks.org/python-programming-language/)T4】

## Python 3 入门

*   **强大、高级**、**和简单:** Python(吉多·范·罗苏姆，国家数学与计算机科学研究院)是一种强大的高级编程语言。语法非常容易阅读和理解，因为它有一个干净的结构。示例:Python 3 有 33 个关键词，Python 2 有 30 个。
*   **解释性质:**可以编译或解释多种语言的程序。Python 具有解释性质，这意味着您只需键入代码并运行它，而无需中间编译步骤。解释器直接执行程序，将每个语句翻译成一个或多个子程序的序列，然后翻译成另一种语言(通常是机器代码)。
*   **流行编程语言:**正在被财富机构迅速接受和改编。Python3 中有即将推出的支持机器学习、数据科学、数据库操作和人工智能的库。Python 也是最热门的技能之一，也是世界上最流行的编程语言之一。在过去的几年里，它被列为年度最受欢迎的技术。
*   **免费:** Python 可以自由安装、使用和分发。不同的平台有不同的版本。所有 Python 版本都是开源的。
*   ***可移植语言(跨平台)*** Python 语言也是一种可移植语言。比方说，如果我们有适用于 Windows、Linux 或 Mac 等平台的 python 代码，我们可以在任何其他平台(安装了 Python 解释器)上运行该代码，而无需对其进行更改。
*   **面向对象:** Python 支持面向对象语言，类和对象的概念应运而生。

## 蟒蛇 2 和蟒蛇 3 的区别

Python 3.0/Python 3000/Py3k 是 Python 的新版本，与 Python 2.x 不兼容(Python 2.0 于 2000 年发布)。下面列出了两者之间的一些主要区别！！

**Python 中的 print:**在 Python2 中，Print 是一个语句，而在 Python3 中，Print 是一个函数，是从无括号到括号的转换！

**示例:**

**在蟒 2**T2】

## 计算机编程语言

```py
# syntax in Python2,
# invalid for Python3
print "Hello GfG !!"
```

**在蟒 3**T2】

## 蟒蛇 3

```py
# syntax for Python3
print("Hello GfG !!")
```

*   **整数除法:**python 2 中的整数除法产生整数。
    例:3/2 会给 1 作为输出！！(但是，3.0/2 或 3/2.0 会给出 1.5 作为输出)。
    根据答案，如果需要，Python3 中的整数除法可以给出浮点值。
    例:3/2 会给出 1.5 作为输出。
*   **兼容性:**蟒 2 很容易移植到蟒 3。在 Python3 中，向后兼容是不可能的。
*   **性能:** Python3 在打字时有帮助，而 Python2 传统上不是打字语言。此外，Python3 在运行时的执行速度比 Python2 更快。
*   **不等于符:**
    **蟒 2**

## 计算机编程语言

```py
a=1
b=2
print(a <> b)
```

**输出:**

```py
True
```

**蟒蛇 3**

## 蟒蛇 3

```py
print('GfG' != 'GfG')
```

**输出:**

```py
False
```

*   **异常:**
    在 python3 中，引入了“as”关键字。

**例:**T2【中蟒 2，

```py
try:

except valueError :

```

在 python3 中，

```py
try:

except valueError as err:

```