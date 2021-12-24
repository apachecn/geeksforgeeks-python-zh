# Python |列表中断点位置上的组元素

> 原文:[https://www . geesforgeks . org/python-group-elements-on-break-position-in-list/](https://www.geeksforgeeks.org/python-group-elements-on-break-positions-in-list/)

很多时候，我们会遇到涉及 Python 分组的问题。有时，我们可能会遇到一个特定的问题，即我们需要对缺失元素上的 N 个元素列表进行拆分和分组。让我们讨论一下执行这项任务的方法。

**方法:使用`itemgetter() + map() + lambda() + groupby()`**
这个任务可以使用上述函数的组合来执行，其中我们可以通过查找列表中索引和值之间的差异来对使用 lambda 函数计算的断点中的元素进行分组。`map()`用于组合逻辑，itemgetter 确保分组是基于值的。仅适用于 Python2。

```
# Python code to demonstrate working of
# Group elements on break positions in list
# using itemgetter() + map() + lambda() + groupby()
from itertools import groupby
from operator import itemgetter

# initialize list
test_list = [1, 2, 4, 5, 6, 8, 9, 11]

# printing original list
print("The original list is : " + str(test_list))

# Group elements on break positions in list
# using itemgetter() + map() + lambda() + groupby()
res = list(map(itemgetter(1), j) for i, j in 
           groupby(enumerate(test_list), lambda (x, y) : x - y))

# printing result
print("Grouping of elements at breaks : " + str(res))
```

**Output :**

```
The original list is : [1, 2, 4, 5, 6, 8, 9, 11]
Grouping of elements at breaks : [[1, 2], [4, 5, 6], [8, 9], [11]]

```