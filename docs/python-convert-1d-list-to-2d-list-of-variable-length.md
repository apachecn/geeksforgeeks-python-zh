# Python |将 1D 列表转换为可变长度的 2D 列表

> 原文:[https://www . geesforgeks . org/python-convert-1d-list-2d-list-of-variable-length/](https://www.geeksforgeeks.org/python-convert-1d-list-to-2d-list-of-variable-length/)

给定 1D 列表“lst”和可变长度列表“var_lst”，编写一个 Python 程序，将给定的 1D 列表转换为给定可变长度的 2D 列表。

**示例:**

```py
Input : lst = [1, 2, 3, 4, 5, 6]
        var_lst = [1, 2, 3]
Output : [[1], [2, 3], [4, 5, 6]]

Input : lst = ['a', 'b', 'c', 'd', 'e']
        var_lst = [3, 2]
Output : [['a', 'b', 'c'], ['d', 'e']]

```

**方法#1 :** 列表切片

```py
# Python3 program to Convert 1D 
# list to 2D list
from itertools import islice

def convert(lst, var_lst):
    idx = 0
    for var_len in var_lst:
        yield lst[idx : idx + var_len]
        idx += var_len

# Driver code
lst = [1, 2, 3, 4, 5, 6]
var_lst = [1, 2, 3]
print(list(convert(lst, var_lst)))
```

**Output:**

```py
[[1], [2, 3], [4, 5, 6]]

```

**方法 2 :** 使用 *itertools.islice()*

```py
# Python3 program to Convert 1D 
# list to 2D list
from itertools import islice

def convert(lst, var_lst):
    it = iter(lst)
    return [list(islice(it, i)) for i in var_lst]

# Driver code
lst = [1, 2, 3, 4, 5, 6]
var_lst = [1, 2, 3]
print(convert(lst, var_lst))
```

**Output:**

```py
[[1], [2, 3], [4, 5, 6]]

```