# Python |检查列表是否包含连续数字

> 原文:[https://www . geesforgeks . org/python-check-if-list-contains-continuous-numbers/](https://www.geeksforgeeks.org/python-check-if-list-contains-consecutive-numbers/)

给定一个数字列表，编写一个 Python 程序来检查该列表是否包含连续的整数。

**示例:**

```
Input : [2, 3, 1, 4, 5]
Output : True

Input : [1, 2, 3, 5, 6]
Output : False

```

让我们讨论一下完成这项任务的几种方法。

**使用`sorted()`接近#1 :**

这种方法使用 Python 的`[sorted()](https://www.geeksforgeeks.org/sorted-function-python/)`函数。我们将排序后的列表与列表的最小和最大整数范围列表进行比较并返回。

```
# Python3 Program to Create list 
# with integers within given range 

def checkConsecutive(l):
    return sorted(l) == list(range(min(l), max(l)+1))

# Driver Code
lst = [2, 3, 1, 4, 5]
print(checkConsecutive(lst))
```

**Output:**

```
True

```

**使用`numpy.diff()`接近#2 :**

Numpy 模块提供了一个函数`diff()`，用于计算沿给定轴的第 n 个离散差值。我们找到排序列表的迭代差，并检查它是否等于 1。

```
# Python3 Program to Create list 
# with integers within given range 
import numpy as np

def checkConsecutive(l):
    n = len(l) - 1
    return (sum(np.diff(sorted(l)) == 1) >= n) 

# Driver Code
lst = [2, 3, 1, 4, 5]
print(checkConsecutive(lst))
```

**Output:**

```
True

```