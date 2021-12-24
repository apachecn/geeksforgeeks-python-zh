# Python |基于值将元组分组到列表中

> 原文:[https://www . geesforgeks . org/python-group-tuple-to-list-based-on-value/](https://www.geeksforgeeks.org/python-group-tuple-into-list-based-on-value/)

有时，在使用 Python 元组时，我们会遇到一个问题，即我们需要根据分配给它的值将元组元素分组到嵌套列表中。这在许多分组应用中非常有用。让我们讨论执行这项任务的某些方法。

**方法一:使用`itemgetter()` +列表理解+`groupby()`+T3】**

上述功能的组合可用于执行该任务。在这种情况下，我们使用`itemgetter()`访问值，并且使用`groupby()`和列表理解来执行分组逻辑。

```
# Python3 code to demonstrate working of
# Group tuple into list based on value
# using itemgetter() + list comprehension + groupby()
from operator import itemgetter
from itertools import groupby

# initialize list 
test_list = [(1, 4), (2, 4), (6, 7), (5, 1), (6, 1), (8, 1)]

# printing original list 
print("The original list : " + str(test_list))

# Group tuple into list based on value
# using itemgetter() + list comprehension + groupby()
res = [[i for i, j in temp]\
      for key, temp in groupby(test_list, key = itemgetter(1))]

# printing result
print("The list after grouping by value : " + str(res))
```

**Output :**

```
The original list : [(1, 4), (2, 4), (6, 7), (5, 1), (6, 1), (8, 1)]
The list after grouping by value : [[1, 2], [6], [5, 6, 8]]

```

**方法二:使用`map() + itemgetter() + groupby()` +列表理解**

这个方法类似于上面的方法，唯一的区别是我们选择了 map 来形成关键字，作为嵌套列表来形成新的结果列表。

```
# Python3 code to demonstrate working of
# Group tuple into list based on value
# using map() + itemgetter() + groupby() + list comprehension
from operator import itemgetter
from itertools import groupby

# initialize list 
test_list = [(1, 4), (2, 4), (6, 7), (5, 1), (6, 1), (8, 1)]

# printing original list 
print("The original list : " + str(test_list))

# Group tuple into list based on value
# using map() + itemgetter() + groupby() + list comprehension
res = [list(map(itemgetter(0), temp)) 
      for (key, temp) in groupby(test_list, itemgetter(1))]

# printing result
print("The list after grouping by value : " + str(res))
```

**Output :**

```
The original list : [(1, 4), (2, 4), (6, 7), (5, 1), (6, 1), (8, 1)]
The list after grouping by value : [[1, 2], [6], [5, 6, 8]]

```