# Python |在给定列表中查找与 k 最接近的数字

> 原文:[https://www . geesforgeks . org/python-查找给定列表中最接近 k 的数字/](https://www.geeksforgeeks.org/python-find-closest-number-to-k-in-given-list/)

给定一个数字列表和一个变量 K，其中 K 也是一个数字，编写一个 Python 程序来查找列表中最接近给定数字 K 的数字

**示例:**

```
Input : lst = [3.64, 5.2, 9.42, 9.35, 8.5, 8], K = 9.1
Output : 9.35

Input : lst = [9, 11, 5, 3, 25, 18], K = 6
Output : 5

```

**方法#1 :** 使用`min()`方法

在这种方法中，我们使用 Python 中的`min` 方法，并应用一个键来找到每个元素与 K 的绝对差异，并返回具有最小差异的元素。

```
# Python3 program to find Closest number in a list

def closest(lst, K):

    return lst[min(range(len(lst)), key = lambda i: abs(lst[i]-K))]

# Driver code
lst = [3.64, 5.2, 9.42, 9.35, 8.5, 8]
K = 9.1
print(closest(lst, K))
```

**Output:**

```
9.35

```

**方法 2 :** 使用`numpy`模块

该方法采用相同的方法，但使用 *numpy* 模块。首先，我们将给定的列表转换成一个数组。求每个元素与 K 的绝对差，从中返回最小值。

```
# Python3 program to find Closest number in a list
import numpy as np
def closest(lst, K):

     lst = np.asarray(lst)
     idx = (np.abs(lst - K)).argmin()
     return lst[idx]

# Driver code
lst = [3.64, 5.2, 9.42, 9.35, 8.5, 8]
K = 9.1
print(closest(lst, K))
```

**Output:**

```
9.35

```