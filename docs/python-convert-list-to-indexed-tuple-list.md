# Python |将列表转换为索引元组列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-indexed-tuple-list/](https://www.geeksforgeeks.org/python-convert-list-to-indexed-tuple-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要将列表转换为元组。这种问题以前已经处理过了。但是有时，我们有它的变体，其中我们需要将元素的索引和元素一起指定为元组。让我们讨论执行这项任务的某些方法。

**方法#1:使用`list() + enumerate()`**
上述功能的组合可用于执行该特定任务。在这种情况下，我们只需将枚举列表传递给 list()，该列表返回第一个元素作为索引，第二个元素作为该索引处的列表元素的元组。

```
# Python3 code to demonstrate working of
# Convert list to indexed tuple
# Using list() + enumerate()

# initializing list
test_list = [4, 5, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Convert list to indexed tuple
# Using list() + enumerate()
res = list(enumerate(test_list))

# Printing result
print("List after conversion to tuple list : " + str(res))
```

**Output :**

```

The original list : [4, 5, 8, 9, 10]
List after conversion to tuple list : [(0, 4), (1, 5), (2, 8), (3, 9), (4, 10)]

```