# Python–连续对逗号删除

> 原文:[https://www . geesforgeks . org/python-continuous-pairs-comma-remove/](https://www.geeksforgeeks.org/python-consecutive-pairs-comma-removal/)

有时候，在列表中工作时，我们可能会遇到一个问题，需要将两个列表中的元素配对。在这种情况下，我们可以有对，我们发现有逗号是打印在元组，我们希望避免它通常。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip() + list comprehension + replace()`**
上述功能的组合可用于执行该任务。在本文中，我们使用 zip()连接列表，并使用 replace()执行删除逗号和连接的任务。

```
# Python3 code to demonstrate 
# Consecutive Pairs Duplication Removal
# using list comprehension + zip() + replace()

# Initializing lists
test_list1 = [1, 2, 3, 4, 5]
test_list2 = [2, 3, 4, 5, 6]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Consecutive Pairs Duplication Removal
# using list comprehension + zip() + replace()
res = str(list(zip(test_list1, test_list2))).replace('), (', ') (')

# printing result 
print ("The combined list after consecutive comma removal : " + str(res))
```

**Output :**

```
The original list 1 is : [1, 2, 3, 4, 5]
The original list 2 is : [2, 3, 4, 5, 6]
The combined list after consecutive comma removal : [(1, 2) (2, 3) (3, 4) (4, 5) (5, 6)]

```