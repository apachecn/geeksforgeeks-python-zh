# Python–从元组列表中获取第 n 列的最大值

> 原文:[https://www . geeksforgeeks . org/python-从元组列表中获取第 n 列的最大值/](https://www.geeksforgeeks.org/python-get-maximum-of-nth-column-from-tuple-list/)

有时，在使用 Python 列表时，我们可能会有一个任务，其中我们需要使用元组列表，并获得其第 N 个索引的最大值。当处理数据信息时，这个问题在 web 开发领域有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `max()`**
该任务可以使用上述功能的组合来执行。在这种情况下，最大索引使用 max()出现，列表理解驱动列表中每个元组的第 N 个索引元素的迭代和访问。

```
# Python3 code to demonstrate working of
# Nth column Maximum in tuple list
# using list comprehension + max()

# initialize list
test_list = [(5, 6, 7), (1, 3, 5), (8, 9, 19)]

# printing original list
print("The original list is : " + str(test_list))

# initialize N
N = 2

# Nth column Maximum in tuple list
# using list comprehension + max()
res = max([sub[N] for sub in test_list])

# printing result
print("Maximum of Nth Column of Tuple List : " + str(res))
```

**Output :**

```
The original list is : [(5, 6, 7), (1, 3, 5), (8, 9, 19)]
Maximum of Nth Column of Tuple List : 19

```