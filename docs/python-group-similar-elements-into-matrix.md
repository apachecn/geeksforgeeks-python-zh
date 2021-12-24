# Python–将相似元素分组到矩阵中

> 原文:[https://www . geesforgeks . org/python-group-相似元素-转化为矩阵/](https://www.geeksforgeeks.org/python-group-similar-elements-into-matrix/)

有时，在使用 Python Matrix 时，我们会遇到一个问题，即我们需要对所有相同的元素进行分组。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [1，3，4，4，2，3]
> **输出** : [[1]，[2]，[3，3]，[4，4]]
> 
> **输入** : test_list = [1，3，4，2]
> **输出** : [[1]，[2]，[3]，[4]]

**方法#1:使用列表理解+ `groupby()`**
以上功能的组合为这个问题提供了可能的解决方案。在本文中，我们使用 groupby()执行分组任务，并在迭代中使用列表理解辅助。

```
# Python3 code to demonstrate working of 
# Group similar elements into Matrix
# Using list comprehension + groupby()
from itertools import groupby

# initializing list
test_list = [1, 3, 5, 1, 3, 2, 5, 4, 2]

# printing original list 
print("The original list : " + str(test_list))

# Group similar elements into Matrix
# Using list comprehension + groupby()
res = [list(val) for key, val in groupby(sorted(test_list))]  

# printing result 
print("Matrix after grouping : " + str(res))
```

**Output :**

```
The original list : [1, 3, 5, 1, 3, 2, 5, 4, 2]
Matrix after grouping : [[1, 1], [2, 2], [3, 3], [4], [5, 5]]

```

**方法 2:使用列表理解+ `Counter()`**
这是解决这个问题的又一种方法。在这种情况下，我们使用 Counter()获得值及其频率，然后使用列表理解将每个元素与频率相乘以获得副本

```
# Python3 code to demonstrate working of 
# Group similar elements into Matrix
# Using list comprehension + Counter()
from collections import Counter

# initializing list
test_list = [1, 3, 5, 1, 3, 2, 5, 4, 2]

# printing original list 
print("The original list : " + str(test_list))

# Group similar elements into Matrix
# Using list comprehension + Counter()
temp = Counter(test_list)
res = [[key] * val for key, val in temp.items()]

# printing result 
print("Matrix after grouping : " + str(res))
```

**Output :**

```
The original list : [1, 3, 5, 1, 3, 2, 5, 4, 2]
Matrix after grouping : [[1, 1], [2, 2], [3, 3], [4], [5, 5]]

```