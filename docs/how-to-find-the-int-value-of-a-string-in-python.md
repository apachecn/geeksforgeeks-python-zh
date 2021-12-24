# 如何在 Python 中找到字符串的 int 值？

> 原文:[https://www . geesforgeks . org/如何在 python 中找到字符串的 int 值/](https://www.geeksforgeeks.org/how-to-find-the-int-value-of-a-string-in-python/)

在 Python 中，我们可以用字符串的形式表示整数值。字符串的 Int 值可以通过使用 python 中称为`**int()**`的内置函数来获得。这里我们可以将 string 作为参数传递给这个函数，这个函数返回一个字符串的 int 值。

## int()

> **语法:** int(字符串，基数)
> **参数:**
> 
> *   **字符串:**由 1 和 0 组成
> *   **基数:**(整数值)数字的基数。
> 
> **返回:**一个整数值，相当于给定基数下的二进制字符串。
> **类型错误:**当除了字符串或整数之外的任何数据类型在其等效位置传递时，返回类型错误。

默认情况下，`int()`假设数字采用十进制表示法。如果我们想要一个属于二进制、十六进制、八进制等其他数字系统的`int` 的字符串表示。我们需要给这个函数传递一个额外的参数来指定基值。基本值是:

*   二进制:2
*   八进制:8
*   十六进制:16

**示例:**

```
Input : "A"  (for base 16)
Output : 10

Input : "510"
Output : 510

```

```
# using base 16
s1 = "A"
print(int(s1, 16))

# using the default base
s2 = "510"
print(int(s2))
```

**输出:**

```
10
510

```