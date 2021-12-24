# Python |根据列表元素存在性过滤元组

> 原文:[https://www . geesforgeks . org/python-filter-元组-根据列表-元素-存在/](https://www.geeksforgeeks.org/python-filter-tuples-according-to-list-element-presence/)

有时，在处理记录时，我们会遇到一个问题，即我们必须从元组列表中筛选所有元组，而元组列表中至少包含一个列表元素。这可以在许多处理数据的领域中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
使用列表理解是一种以速记方式执行这项任务的蛮力方法。在这种情况下，我们只检查每个元组，并检查它是否包含目标列表中的任何元素。

```
# Python3 code to demonstrate working of
# Filter tuples according to list element presence
# using list comprehension

# initialize list of tuple
test_list = [(1, 4, 6), (5, 8), (2, 9), (1, 10)]

# initialize target list 
tar_list = [6, 10]

# printing original tuples list
print("The original list : " + str(test_list))

# Filter tuples according to list element presence
# using list comprehension
res = [tup for tup in test_list if any(i in tup for i in tar_list)]

# printing result
print("Filtered tuple from list are : " + str(res))
```

**Output :**

```
The original list : [(1, 4, 6), (5, 8), (2, 9), (1, 10)]
Filtered tuple from list are : [(1, 4, 6), (1, 10)]

```