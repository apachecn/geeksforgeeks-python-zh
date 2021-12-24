# Python |列表中相同的连续分组

> 原文:[https://www . geesforgeks . org/python-相同-连续-列表中分组/](https://www.geeksforgeeks.org/python-identical-consecutive-grouping-in-list/)

有时，在使用 Python 列表时，我们可能会遇到需要执行分组的问题。可能会有一个特殊的问题，我们需要对连续出现的元素进行分组。解决这个问题是有用的。让我们讨论一下实现这一点的具体方法。

**方法:使用`groupby()` +列表理解**
这个任务可以使用 Python 提供的内置`groupby()`轻松完成。这可以与逻辑组合和迭代的列表理解相结合。

```
# Python3 code to demonstrate working of
# Identical Consecutive Grouping in list
# using groupby() + list comprehension
from itertools import groupby

# initialize list
test_list = [4, 4, 5, 5, 5, 7, 7, 8, 8, 8]

# printing original list
print("The original list is : " + str(test_list))

# Identical Consecutive Grouping in list
# using groupby() + list comprehension
res = [list(y) for x, y in groupby(test_list)]

# printing result
print("List after grouping is : " + str(res))
```

**Output :**

```
The original list is : [4, 4, 5, 5, 5, 7, 7, 8, 8, 8]
List after grouping is : [[4, 4], [5, 5, 5], [7, 7], [8, 8, 8]]

```