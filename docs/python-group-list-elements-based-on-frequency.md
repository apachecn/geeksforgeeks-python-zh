# Python |基于频率分组列表元素

> 原文:[https://www . geesforgeks . org/python-group-list-elements-based-on-frequency/](https://www.geeksforgeeks.org/python-group-list-elements-based-on-frequency/)

给定一个元素列表，编写一个 Python 程序，将列表元素及其在元组中的频率分组。

**示例:**

```
Input : [1, 3, 4, 4, 1, 5, 3, 1]
Output : [(1, 3), (3, 2), (4, 2), (5, 1)]

Input : ['x', 'a', 'x', 'y', 'a', 'x']
Output : [('x', 3), ('a', 2), ('y', 1)]

```

**方法#1 :** 列表理解

我们可以使用列表理解来形成每个元素的元组及其出现次数，并将其存储在“res”中，但这将包含重复的第一个元素。因此，要删除重复的第一个元素，我们使用`OrderedDict(res).items()`。

```
# Python3 program to Grouping list 
# elements based on frequency
from collections import OrderedDict 

def group_list(lst):

    res =  [(el, lst.count(el)) for el in lst]
    return list(OrderedDict(res).items())

# Driver code
lst = [1, 3, 4, 4, 1, 5, 3, 1]
print(group_list(lst))
```

**Output:**

```
[(1, 3), (3, 2), (4, 2), (5, 1)]

```

**方法 2 :** 使用`collections.Counter()`

`collections.Counter()`提供两种直接方法`keys()`和`values()`提供元素及其出现。最后，使用 Python `zip()`方法将它们压缩在一起。

```
# Python3 program to Grouping list 
# elements based on frequency
from collections import Counter

def group_list(lst):

    return list(zip(Counter(lst).keys(), Counter(lst).values()))

# Driver code
lst = [1, 3, 4, 4, 1, 5, 3, 1]
print(group_list(lst))
```

**Output:**

```
[(1, 3), (3, 2), (4, 2), (5, 1)]

```