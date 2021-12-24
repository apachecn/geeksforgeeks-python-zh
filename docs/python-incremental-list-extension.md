# Python–增量列表扩展

> 原文:[https://www . geesforgeks . org/python-增量-列表-扩展/](https://www.geeksforgeeks.org/python-incremental-list-extension/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要以非常定制的方式扩展列表。我们可能不得不重复列表的内容，在这样做的同时，每次新列表都必须在原始列表中添加一个数字。这种增量式扩展在许多领域都有应用。让我们讨论一下执行这项任务的方法。

**方法:使用列表理解**
这个任务可以用蛮力的方式来完成，但是使用列表理解实现的时间越短越好。在这种情况下，我们分两步执行任务，首先我们制作一个帮助列表来形成一个添加因子列表，然后使用原始列表累积结果。

```py
# Python3 code to demonstrate working of
# Incremental List Extension
# Using list comprehension

# initializing list
test_list = [7, 8, 9]

# printing original list
print("The original list is : " + str(test_list))

# Extension factor
N = 4

# Addition factor 
M = 3

# Incremental List Extension
# Using list comprehension
temp = [1 * M**i for i in range(N)]
temp[0] = 0
res = list([ele + tele for tele in temp for ele in test_list])

# printing result 
print("List after extension and addition : " + str(res))
```

**Output :**

```py
The original list is : [7, 8, 9]
List after extension and addition : [7, 8, 9, 10, 11, 12, 16, 17, 18, 34, 35, 36]

```