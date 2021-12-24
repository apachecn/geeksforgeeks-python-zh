# Python–字符串列表中所有可能的连接

> 原文:[https://www . geeksforgeeks . org/python-所有可能的字符串串联列表/](https://www.geeksforgeeks.org/python-all-possible-concatenations-in-string-list/)

有时，在处理字符串列表时，我们会遇到一个问题，即我们需要对列表中出现的所有字符串执行所有可能的连接。这种问题可能发生在日常编程和学校编程等领域。

让我们讨论一下执行这项任务的方法。

> **输入** : test_list = ['Gfg '，' Best']
> **输出** : ['Gfg '，' Best '，' Gfg Best ']
> 
> **输入** : test_list = ['Gfg']
> **输出** : ['Gfg']

**方法:使用排列()+连接()+循环**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 join()执行连接任务，并使用置换()执行所有可能的组合提取。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All possible concatenations in String List
# Using permutations() + loop
from itertools import permutations

# initializing list
test_list = ['Gfg', 'is', 'Best']

# printing original list
print("The original list : " + str(test_list))

# All possible concatenations in String List
# Using permutations() + loop
temp = []
for idx in range(1, len(test_list) + 1):
    temp.extend(list(permutations(test_list, idx)))
res = []
for ele in temp:
    res.append("".join(ele))

# printing result
print("All String combinations : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best']
All String combinations : ['Gfg', 'is', 'Best', 'Gfgis', 'GfgBest', 'isGfg', 'isBest', 'BestGfg', 'Bestis', 'GfgisBest', 'GfgBestis', 'isGfgBest', 'isBestGfg', 'BestGfgis', 'BestisGfg']
```