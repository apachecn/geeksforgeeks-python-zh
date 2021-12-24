# Python |记录列表差异

> 原文:[https://www . geesforgeks . org/python-差异记录列表/](https://www.geeksforgeeks.org/python-difference-in-record-lists/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要找到收到的两个列表之间的差异记录。这是一个非常常见的问题，记录通常以元组的形式出现。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
可以选择列表理解作为在一行中执行该任务的方法，而不是运行循环来寻找不同的元素。在这种情况下，我们只是迭代单个列表，并检查是否有任何元素出现在其他列表中。

```
# Python3 code to demonstrate working of
# Difference in Record Lists
# Using list comprehension

# Initializing lists
test_list1 = [('gfg', 1), ('is', 2), ('best', 3)]
test_list2 = [('i', 3), ('love', 4), ('gfg', 1)]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Intersection in Tuple Records Data
# Using list comprehension
res = [ele1 for ele1 in test_list1 for ele2 in test_list2 if ele1 == ele2]
res = list(set(res) ^ set(test_list1))

# printing result
print("The difference of data records is : " + str(res))
```

**Output :**

```
The original list 1 is : [('gfg', 1), ('is', 2), ('best', 3)]
The original list 2 is : [('i', 3), ('love', 4), ('gfg', 1)]
The difference of data records is : [('best', 3), ('is', 2)]

```