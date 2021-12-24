# Python–过滤范围长度元组

> 原文:[https://www . geesforgeks . org/python-filter-range-length-元组/](https://www.geeksforgeeks.org/python-filter-range-length-tuples/)

有时，在处理记录时，我们可能希望以这样一种方式过滤记录，即我们需要丢弃不包含构成记录所需的确切元素数且位于某个范围内的记录。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `len()`**
在该方法中，我们只需遍历列表，丢弃与构成记录所需的匹配范围长度不匹配的元组。长度的计算是由 len()完成的。

```
# Python3 code to demonstrate working of
# Filter Range Length Tuples
# Using list comprehension + len()

# Initializing list
test_list = [(4, ), (5, 6), (2, 3, 5), (5, 6, 8, 2), (5, 9)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing desired lengths 
i, j = 2, 3

# Filter Range Length Tuples
# Using list comprehension + len()
res = [sub for sub in test_list if len(sub) >= i and len(sub) <= j]

# printing result
print("The tuple list after filtering range records : " + str(res))
```

**Output :**

```
The original list is : [(4, ), (5, 6), (2, 3, 5), (5, 6, 8, 2), (5, 9)]
The tuple list after filtering range records : [(5, 6), (2, 3, 5), (5, 9)]

```