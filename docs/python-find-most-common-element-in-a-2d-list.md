# Python |查找 2D 列表中最常见的元素

> 原文:[https://www . geesforgeks . org/python-find-最常见元素-in-a-2d-list/](https://www.geeksforgeeks.org/python-find-most-common-element-in-a-2d-list/)

给定一个 2D 列表(长度可能相同，也可能不同)，编写一个 Python 程序来查找给定 2D 列表中最常见的元素。

**示例:**

```
Input : [[10, 20, 30], [20, 50, 10], [30, 50, 10]]
Output : 10

Input : [['geeks', 'wins'], ['techie', 'wins']]
Output : wins

```

**方法#1 :** 使用`max()`功能

第一种 Python 方法是使用 Python 的 *max()* 方法。我们首先展平 2D 列表，然后简单地应用 max()方法找出所有元素中最大出现的元素。

```
# Python3 program to find most 
# common element in a 2D list

def mostCommon(lst):
    flatList = [el for sublist in lst for el in sublist]
    return max(flatList, key = flatList.count)

# Driver code
lst = [[10, 20, 30], [20, 50, 10], [30, 50, 10]]
print(mostCommon(lst))
```

**Output:**

```
10

```

还有另一种方法来展平列表，即`chain.from_iterable()`，这产生了另一种方法。

```
# Python3 program to find most 
# common element in a 2D list
from itertools import chain

def mostCommon(lst):
    flatList = list(chain.from_iterable(lst))
    return max(flatList, key=flatList.count)

# Driver code
lst = [[10, 20, 30], [20, 50, 10], [30, 50, 10]]
print(mostCommon(lst))
```

**Output:**

```
10

```

**方法 2 :** 使用来自*集合*模块的`most_common()`

*most_common()* 用于产生 n 个最常遇到的输入值的序列。因此，我们简单地展平列表，并使用上述方法找到最常见的元素。

```
# Python3 program to find most 
# common element in a 2D list
from itertools import chain
from collections import Counter

def mostCommon(lst):
    flatList = chain.from_iterable(lst)
    return Counter(flatList).most_common(1)[0][0]

# Driver code
lst = [[10, 20, 30], [20, 50, 10], [30, 50, 10]]
print(mostCommon(lst))
```

**Output:**

```
10

```