# Python–双元素行组合

> 原文:[https://www . geesforgeks . org/python-双元素-行-组合/](https://www.geeksforgeeks.org/python-dual-element-rows-combinations/)

有时，在处理数据时，我们会遇到一个问题，需要在列表中查找组合。这可以是一个简单的。但是有时，我们需要执行它的一个变体，并拥有一个双元素行而不是单元素。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `enumerate()`**
以上功能的组合可以用来执行这个任务。在本文中，我们遍历列表，并使用理解和枚举()执行组合。

```
# Python3 code to demonstrate 
# Dual element Rows Combinations
# using list comprehension + enumerate()
from collections import defaultdict

# Initializing list
test_list = [[3, 4], [5, 6], [7, 8]]

# printing original list 
print("The original list is : " + str(test_list))

# Dual element Rows Combinations
# using list comprehension + enumerate()
res = [test_list[idx - len(test_list)] + test_list[idx + 1 - len(test_list)] 
      for idx, ele in enumerate(test_list)]

# printing result 
print ("Combination of dual rows list is : " + str(res))
```

**Output :**

```
The original list is : [[3, 4], [5, 6], [7, 8]]
Combination of dual rows list is : [[3, 4, 5, 6], [5, 6, 7, 8], [7, 8, 3, 4]]

```