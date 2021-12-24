# Python–交叉元组求和分组

> 原文:[https://www . geesforgeks . org/python-交叉元组-求和-分组/](https://www.geeksforgeeks.org/python-cross-tuple-summation-grouping/)

有时，在处理 Python 元组记录时，我们可能会遇到一个问题，即我们需要对元组对的第一个元素执行求和分组，类似于元组的第二个元素。这种问题可以在日常编程中应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(1，5)，(7，4)，(9，6)，(11，6)]
> **输出** : [(7，4)，(1，5)，(20，6)]
> 
> **输入** : test_list = [(1，8)]
> **输出** : [(1，8)]

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们检查相似的第二元素，并执行求和，直到那时，并执行累积分组。

```
# Python3 code to demonstrate working of 
# Cross tuple summation grouping
# Using loop

# initializing list
test_list = [(4, 5), (7, 5), (8, 6), (10, 6), (10, 4), (6, 7), (3, 7)]

# printing original list
print("The original list is : " + str(test_list))

# Concatenate Similar Key values
# Using loop
temp = dict()
for ele1, ele2 in test_list:
    temp[ele2] = temp.get(ele2, 0) + ele1
res = [(ele2, ele1) for (ele1, ele2) in temp.items()]

# printing result 
print("The grouped records are : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5), (7, 5), (8, 6), (10, 6), (10, 4), (6, 7), (3, 7)]
The grouped records are : [(10, 4), (11, 5), (18, 6), (9, 7)]

```

**方法二:使用`groupby() + sum() + zip()` +列表理解**
以上功能的组合可以解决这个问题。在本文中，我们使用 sum()执行求和的任务。分组任务由 groupby()完成。

```
# Python3 code to demonstrate working of 
# Cross tuple summation grouping
# Using groupby() + sum() + zip() + list comprehension
from itertools import groupby

# initializing list
test_list = [(4, 5), (7, 5), (8, 6), (10, 6), (10, 4), (6, 7), (3, 7)]

# printing original list
print("The original list is : " + str(test_list))

# Concatenate Similar Key values
# Using groupby() + sum() + zip() + list comprehension
res = [(sum(next(zip(*ele))), key) for key, ele in groupby(
                       test_list, key = lambda tup:tup[1])]

# printing result 
print("The grouped records are : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5), (7, 5), (8, 6), (10, 6), (10, 4), (6, 7), (3, 7)]
The grouped records are : [(10, 4), (11, 5), (18, 6), (9, 7)]

```