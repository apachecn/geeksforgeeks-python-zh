# Python–逆字典值列表

> 原文:[https://www . geesforgeks . org/python-reverse-dictionary-values-list/](https://www.geeksforgeeks.org/python-inverse-dictionary-values-list/)

给定一个字典作为值列表，反转它，即将列表中的元素映射到关键字，并创建新的值列表。

> **输入** : test_dict = {1: [2，3]，2: [3]，3: [1]}
> **输出** : {2: [1]，3: [1，2]，1: [3]}
> **解释**:列出用键映射的元素。
> 
> **输入** : test_dict = {1: [2，3，4]}
> **输出** : {2: [1]，3: [1]，4: [1]}
> **解释**:列出用键映射的元素。

**方法:使用 defaultdict() +循环**

这是执行这项任务的一种方式。在本文中，我们使用字典列表初始化结果关键字，并使用循环迭代为每个值分配其关键字，并重新构建结果字典值列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Inverse Dictionary Values List
# Using 
from collections import defaultdict

# initializing dictionary
test_dict = {1: [2, 3], 2: [3], 3: [1], 4: [2, 1]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing empty list as Values
res = defaultdict(list)                                                                 

# using loop to perform reverse mapping
for keys, vals in test_dict.items(): 
   for val in vals: 
       res[val].append(keys)

# printing result 
print("The required result : " + str(dict(res))) 
```

**Output**

```py
The original dictionary is : {1: [2, 3], 2: [3], 3: [1], 4: [2, 1]}
The required result : {2: [1, 4], 3: [1, 2], 1: [3, 4]}

```