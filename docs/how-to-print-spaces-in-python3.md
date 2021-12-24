# 如何在 Python3 中打印空格？

> 原文:[https://www . geesforgeks . org/how-to-print-spaces-in-pyt 3/](https://www.geeksforgeeks.org/how-to-print-spaces-in-python3/)

在本文中，我们将学习如何在 Python 编程语言中打印空格或多个空格。**Python 语言中的间距**比其他编程语言要简单的多。在 C 语言中，要打印 10 个空格，需要使用一个循环，而在 python 中，不使用循环来打印空格数。

以下是打印空间的示例:

**示例 1:** 打印空格的简单方法

## 蟒蛇 3

```
# Python program to print spaces

# No spaces
print("GeeksForGeeks")

# To print the blank lines
print(' ')

# Also print the blanks
print(" ")

# To print the spaces in sentence
print("Geeks  For    Geeks")
```

**输出:**

```
GeeksForGeeks

Geeks  For    Geeks

```

**示例 2:** 在单个打印语句中打印时，打印两个值之间的空格。

## 蟒蛇 3

```
# Python program to print spaces
x = 1
y = 2

# use of "," symbol
print("x:",x)
print("y:",y)
print(x,"+",y,"=",x+y)
```

**输出:**

```
x: 1
y: 2
1 + 2 = 3

```

**示例 3:** 在两个值之间打印多个空格。

## 蟒蛇 3

```
# Python program to print spaces

# To print the single spaces in sentence
print("Geeks"+" "+"For"+" "+"Geeks")
print("Geeks","For","Geeks")

# to print spaces by given times
print("Geeks"+" "*3+"For"+" "*3+"Geeks")
print("Geeks"+" "*5+"For"+" "*10+"Geeks")
```

**输出:**

```
Geeks For Geeks
Geeks For Geeks
Geeks   For   Geeks
Geeks     For          Geeks

```