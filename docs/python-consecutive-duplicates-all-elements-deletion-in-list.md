# Python |连续重复列表中所有元素删除

> 原文:[https://www . geesforgeks . org/python-连续-重复-所有元素-列表中删除/](https://www.geeksforgeeks.org/python-consecutive-duplicates-all-elements-deletion-in-list/)

有时，在使用 Python 列表时，可能会出现过滤列表以删除重复项的问题。这个问题的解决方案之前已经讨论过了。但是有时，我们可能会遇到一个问题，如果连续出现 1 次以上，我们需要删除重复和元素本身。这类问题也可能发生在日常编程和其他应用程序中。让我们讨论一种可以执行这项任务的速记方法。

**方法:使用列表理解+ `groupby() + sum()`**
这个任务可以使用以上功能的组合来执行。第一步是使用`groupby()`将元素分组为副本，然后如果它们出现超过 0 次，则删除它们，即只包括那些出现一次的元素。本次盘点任务由`sum()`处理

```
# Python3 code to demonstrate working of
# Consecutive duplicates all elements deletion in list
# using list comprehension + sum() + groupby()
from itertools import groupby

# initialize list
test_list = [1, 1, 3, 4, 4, 4, 5, 6, 6, 7, 8, 8, 6]

# printing original list
print("The original list is : " + str(test_list))

# Consecutive duplicates all elements deletion in list
# using list comprehension + sum() + groupby()
res = [i for i, j in groupby(test_list) if sum(1 for x in j) < 2]

# printing result
print("List after consecutive duplicates elements deletion : " + str(res))
```

**Output :**

```
The original list is : [1, 1, 3, 4, 4, 4, 5, 6, 6, 7, 8, 8, 6]
List after consecutive duplicates elements deletion : [3, 5, 7, 6]

```