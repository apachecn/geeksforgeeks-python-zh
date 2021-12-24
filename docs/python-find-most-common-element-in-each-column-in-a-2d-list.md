# Python |在 2D 列表的每一列中查找最常见的元素

> 原文:[https://www . geeksforgeeks . org/python-在 2d 列表中的每列中查找最常见的元素/](https://www.geeksforgeeks.org/python-find-most-common-element-in-each-column-in-a-2d-list/)

给定一个 2D 列表，编写一个 Python 程序，在 2D 列表的每一列中找到最常见的元素。

**示例:**

```py
Input : [[1, 1, 3],
        [2, 3, 3],
        [3, 2, 2],
        [2, 1, 3]]
Output : [2, 1, 3]

Input : [['y', 'y'],
         ['y', 'x'],
         ['x', 'x']]
Output : ['y', 'x']

```

**方法#1 :** 使用*系列*模块中的*最常见()*

*most_common()* 返回一个最常见元素的列表 *n* 及其从最常见到最不常见的计数。因此，使用列表理解，我们可以很容易地找到每个列中最常见的元素。

```py
# Python3 program to find most common 
# element in each column in a 2D list
from collections import Counter

def mostCommon(lst):

    return [Counter(col).most_common(1)[0][0] for col in zip(*lst)]

# Driver code
lst = [[1, 1, 3],
       [2, 3, 3],
       [3, 2, 2],
       [2, 1, 3]]
print(mostCommon(lst))
```

**Output:**

```py
[2, 1, 3]

```

**方法#3 :** 使用*模式()*从*统计*模块

```py
# Python3 program to find most common 
# element in each column in a 2D list
from scipy.stats import mode
import numpy as np

def mostCommon(lst):

    val, count = mode(lst, axis = 0)
    return val.ravel().tolist()

# Driver code
lst = [[1, 1, 3],
       [2, 3, 3],
       [3, 2, 2],
       [2, 1, 3]]
print(mostCommon(lst))
```

**Output:**

```py
[2, 1, 3]

```