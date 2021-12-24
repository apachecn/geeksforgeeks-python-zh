# Python |获取每个子列表的最后一个元素

> 原文:[https://www . geesforgeks . org/python-get-每个子列表的最后一个元素/](https://www.geeksforgeeks.org/python-get-last-element-of-each-sublist/)

给定一个列表列表，编写一个 Python 程序来提取给定列表列表中每个子列表的最后一个元素。

**示例:**

```py
Input : [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
Output : [3, 5, 9]

Input : [['x', 'y', 'z'], ['m'], ['a', 'b'], ['u', 'v']]
Output : ['z', 'm', 'b', 'v']

```

**方法#1 :** 列表理解

```py
# Python3 program to extract first and last 
# element of each sublist in a list of lists

def Extract(lst):
    return [item[-1] for item in lst]

# Driver code
lst = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
print(Extract(lst))
```

**Output:**

```py
[3, 5, 9]

```

**接近#2 :** 使用*压缩*和拆包(*)操作符

该方法使用带有*或解包运算符的 *zip* ，该运算符将“lst”中的所有项作为参数传递给 zip 函数。提取列表的最后一项有一个小技巧，不要使用直接压缩，而是使用反向列表迭代器。

```py

# Python3 program to extract first and last 
# element of each sublist in a list of lists

def Extract(lst):
    return list(zip(*[reversed(el) for el in lst]))[0]

# Driver code
lst = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
print(Extract(lst))
```

**Output:**

```py
(3, 5, 9)

```

另一种使用`zip` 的方式是和 Python `map`一起使用，传递`reversed`作为函数。

```py
def Extract(lst):
    return list(list(zip(*map(reversed, lst)))[0])
```

**使用`itemgetter()`接近#3 :**

```py
# Python3 program to extract first and last 
# element of each sublist in a list of lists
from operator import itemgetter

def Extract(lst):
    return list( map(itemgetter(-1), lst ))

# Driver code
lst = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
print(Extract(lst))
```

**Output:**

```py
[3, 5, 9]

```