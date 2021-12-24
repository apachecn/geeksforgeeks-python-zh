# Python–相似索引元素的组记录

> 原文:[https://www . geesforgeks . org/python-group-records-on-like-index-elements/](https://www.geeksforgeeks.org/python-group-records-on-similar-index-elements/)

有时，在处理 Python 记录时，我们会遇到一个问题，即我们需要根据其余索引的相似性对元组的特定索引进行分组。这类问题在网络开发领域可能会有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(4，5，10)，(4，5，7)，(4，5，12)]
> **输出** : ((4，5，[10，7，12])，)
> 
> **输入** : test_list = [(4，5，10)]
> **输出** : [(4，5，[10])

**方法#1:使用`defaultdict()` +循环**
上述函数的组合提供了一种解决这个问题的强力方法。在这种情况下，我们使用 defaultdict()在其余元素相等的基础上将元素和 club 组合成一个。

```py
# Python3 code to demonstrate working of 
# Group Records on Similar index elements
# Using defaultdict() + loop
from collections import defaultdict

# initializing list
test_list = [(4, 7, 13), (4, 5, 7), (6, 7, 10), (4, 5, 15), (6, 7, 12)]

# printing original list
print("The original list is : " + str(test_list))

# Group Records on Similar index elements
# Using defaultdict() + loop
temp = defaultdict(list)
for a, b, c in test_list:
    temp[a, b].append(c)
res = tuple((*key, val) for key, val in temp.items())

# printing result 
print("Tuples after grouping : " + str(res)) 
```

**Output :**

```py
The original list is : [(4, 7, 13), (4, 5, 7), (6, 7, 10), (4, 5, 15), (6, 7, 12)]
Tuples after grouping : ((4, 7, [13]), (4, 5, [7, 15]), (6, 7, [10, 12]))

```

**方法 2:使用 `groupby() + generator expression`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 groupby()对所有元素进行分组，并使用生成器表达式生成元组列表。此方法需要排序列表。

```py
# Python3 code to demonstrate working of 
# Group Records on Similar index elements
# Using groupby() + generator expression
from itertools import groupby

# initializing list
test_list = [(4, 7, 13), (4, 5, 7), (6, 7, 10), (4, 5, 15), (6, 7, 12)]

# printing original list
print("The original list is : " + str(test_list))

# Group Records on Similar index elements
# Using groupby() + generator expression
test_list.sort()
res = tuple((*key, [tup[-1] for tup in val]) for key, val in groupby(test_list, lambda tup: tup[:2]))

# printing result 
print("Tuples after grouping : " + str(res)) 
```

**Output :**

```py
The original list is : [(4, 7, 13), (4, 5, 7), (6, 7, 10), (4, 5, 15), (6, 7, 12)]
Tuples after grouping : ((4, 7, [13]), (4, 5, [7, 15]), (6, 7, [10, 12]))

```