# Python 中最多两个数字

> 原文:[https://www . geesforgeks . org/python 中最多两个数字/](https://www.geeksforgeeks.org/maximum-of-two-numbers-in-python/)

给定两个数字，编写一个 Python 代码来找到这两个数字的最大值。

**示例:**

```
Input: a = 2, b = 4
Output: 4

Input: a = -1, b = -4
Output: -1
```

**方法#1:** 这是一种天真的方法，我们将使用 [if-else](https://www.geeksforgeeks.org/python-if-else/) 语句比较两个数字，并相应地打印输出。

**示例:**

## 蟒蛇 3

```
# Python program to find the
# maximum of two numbers

def maximum(a, b):

    if a >= b:
        return a
    else:
        return b

# Driver code
a = 2
b = 4
print(maximum(a, b))
```

**Output**

```
4
```

**方法 2:** 使用 [max()](https://www.geeksforgeeks.org/max-min-python/) 函数
该函数用于查找作为其参数传递的值的最大值。

**示例:**

## 蟒蛇 3

```
# Python program to find the
# maximum of two numbers

a = 2
b = 4

maximum = max(a, b)
print(maximum)
```

**Output**

```
4
```

**方法 3:** 使用[三元算子](https://www.geeksforgeeks.org/ternary-operator-in-python/)

该运算符也称为条件表达式，是基于条件为真或假来计算某个值的运算符。它只允许在一行中测试一个条件

**示例:**

## 蟒蛇 3

```
# Python program to find the
# maximum of two numbers

# Driver code
a = 2
b = 4

# Use of ternary operator
print(a if a >= b else b)

# This code is contributed by AnkThon
```

**Output**

```
4
```