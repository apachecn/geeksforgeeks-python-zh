# Python |获取每个子列表的第一个元素

> 原文:[https://www . geesforgeks . org/python-get-first-element-of-after-list/](https://www.geeksforgeeks.org/python-get-first-element-of-each-sublist/)

给定一个列表列表，编写一个 Python 程序来提取给定列表列表中每个子列表的第一个元素。

**示例:**

```
Input : [[1, 2], [3, 4, 5], [6, 7, 8, 9]]
Output : [1, 3, 6]

Input : [['x', 'y', 'z'], ['m'], ['a', 'b'], ['u', 'v']]
Output : ['x', 'm', 'a', 'u']

```

**方法#1 :** 列表理解

```
# Python3 program to extract first and last 
# element of each sublist in a list of lists

def Extract(lst):
    return [item[0] for item in lst]

# Driver code
lst = [[1, 2], [3, 4, 5], [6, 7, 8, 9]]
print(Extract(lst))
```

**Output:**

```
[1, 3, 6]

```

**接近#2 :** 使用*压缩*和拆包(*)操作符

该方法使用带有*或解包运算符的 *zip* ，该运算符将“lst”中的所有项作为参数传递给 zip 函数。因此，所有第一个元素将成为压缩列表的第一个元组。因此，返回第 0 <sup>个</sup>元素将解决该目的。

```
# Python3 program to extract first and last 
# element of each sublist in a list of lists

def Extract(lst):
    return list(list(zip(*lst))[0])

# Driver code
lst = [[1, 2], [3, 4, 5], [6, 7, 8, 9]]
print(Extract(lst))
```

**Output:**

```
[1, 3, 6]

```

另一种使用 *zip* 的方法如下:-

```
def Extract(lst):
    return list(next(zip(*lst)))
```

**使用`itemgetter()`接近#3 :**

```
# Python3 program to extract first and last 
# element of each sublist in a list of lists
from operator import itemgetter

def Extract(lst):
    return list( map(itemgetter(0), lst ))

# Driver code
lst = [[1, 2], [3, 4, 5], [6, 7, 8, 9]]
print(Extract(lst))
```

**Output:**

```
[1, 3, 6]

```