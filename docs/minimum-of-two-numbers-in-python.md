# Python 中最少两个数字

> 原文:[https://www . geesforgeks . org/python 中最少两个数字/](https://www.geeksforgeeks.org/minimum-of-two-numbers-in-python/)

给定两个数字，编写一个 Python 代码来找到这两个数字的最小值。

**示例:**

```
Input: a = 2, b = 4
Output: 2

Input: a = -1, b = -4
Output: -4

```

**方法#1:** 这是一种简单的方法，我们将使用 [if-else](https://www.geeksforgeeks.org/python-if-else/) 语句比较数字，并相应地打印输出。

**示例:**

```
# Python program to find the
# minimum of two numbers

def minimum(a, b):

    if a <= b:
        return a
    else:
        return b

# Driver code
a = 2
b = 4
print(minimum(a, b))
```

**输出:**

```
2
```

**方法 2:** 使用[分钟()](https://www.geeksforgeeks.org/max-min-python/)功能

此函数用于查找作为其参数传递的最小值。

**示例:**

```
# Python program to find the
# minimum of two numbers

a = 2
b = 4

minimum = min(a, b)
print(minimum)
```

**输出:**

```
2
```