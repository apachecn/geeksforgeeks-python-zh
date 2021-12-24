# 在 Python 中求未知输入数的平均值

> 原文:[https://www . geesforgeks . org/find-未知输入数的平均值-in-python/](https://www.geeksforgeeks.org/find-the-average-of-an-unknown-number-of-inputs-in-python/)

**先决条件:**[* Python 中的参数和* * kwargs](https://www.geeksforgeeks.org/args-kwargs-python/)
Python 中函数定义中的特殊语法*args 用于向函数传递可变数量的参数。它用于传递非关键字、可变长度的参数列表。语法是使用符号*接受可变数量的参数；按照惯例，它经常与 args 一词连用。在本文中，任务是找到未知输入数的平均值。
**例:**

```
Input : 1, 2, 3
Output : 2.00

Input : 2, 6, 4, 8
Output: 5.00
```

下面是实现。

## 蟒蛇 3

```
# function that takes arbitrary
# number of inputs
def avgfun(*n):
    sums = 0

    for t in n:
        sums = sums + t

    avg = sums / len(n)
    return avg

# Driver Code
result1 = avgfun(1, 2, 3)
result2 = avgfun(2, 6, 4, 8)

# Printing average of the list
print(round(result1, 2))
print(round(result2, 2))
```

**输出:**

```
2.0
5.0
```