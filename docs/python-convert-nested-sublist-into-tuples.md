# Python |将嵌套子列表转换为元组

> 原文:[https://www . geeksforgeeks . org/python-convert-nested-sublist-into-元组/](https://www.geeksforgeeks.org/python-convert-nested-sublist-into-tuples/)

有时，在处理大量数据时，我们可能会遇到每个数据点都由几个元素组成，并且需要作为单个单元进行处理的情况。为此，我们有时可能会收到一个矩阵，它的组成数据点也是列表，这没有多大意义和整体性，可能需要转换为元组。让我们讨论执行这项任务的某些方法。

**方法一:使用`tuple()` +列表理解**
这是解决这个问题的一条线方法。在这种情况下，我们只需遍历最里面的子列表，并使用`tuple()`将每个列表转换为元组。

```py
# Python3 code to demonstrate working of
# Convert nested sublist into tuples
# Using tuple() + list comprehension

# Initializing list
test_list = [[[1, 2, 3], [4, 6, 7]], [[6, 9, 8], [10, 11, 12]]]

# printing original list
print("The original list is : " + str(test_list))

# Convert nested sublist into tuples
# Using tuple() + list comprehension
res = [[tuple(ele) for ele in sub] for sub in test_list]

# printing result
print("The data after conversion to tuple is : " + str(res))
```

**Output :**

```py
The original list is : [[[1, 2, 3], [4, 6, 7]], [[6, 9, 8], [10, 11, 12]]]
The data after conversion to tuple is : [[(1, 2, 3), (4, 6, 7)], [(6, 9, 8), (10, 11, 12)]]

```