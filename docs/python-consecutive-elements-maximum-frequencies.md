# Python–连续元素最大频率

> 原文:[https://www . geeksforgeeks . org/python-连续元素-最大频率/](https://www.geeksforgeeks.org/python-consecutive-elements-maximum-frequencies/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要提取连续元素的最大频率。这种问题可能出现在许多领域，如日常编程和竞争性编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [7，6，7，7]
> **输出** : {7: 2，6: 1}
> 
> **输入** : test_list = [7，7，7]
> **输出** : {7: 3}

**方法#1:使用 loop + `groupby()`**
以上功能的组合可以用来执行这个任务。在这种情况下，我们将所有连续的元素分组，然后使用字典关键字与当前最大值进行比较来生成最大频率字典。

```
# Python3 code to demonstrate working of 
# Consecutive elements maximum frequencies
# Using loop + groupby()
from itertools import groupby

# initializing list
test_list = [5, 6, 7, 7, 6, 6, 5, 7]

# printing original list
print("The original list is : " + str(test_list))

# Consecutive elements maximum frequencies
# Using loop + groupby()
res = {}
for key, val in groupby(test_list):
    sub = sum(1 for _ in val)
    if res.get(key, float('-inf')) < sub:
        res[key] = sub

# printing result 
print("The maximum frequencies : " + str(res)) 
```

**Output :**

```
The original list is : [5, 6, 7, 7, 6, 6, 5, 7]
The maximum frequencies : {5: 1, 6: 2, 7: 2}

```

**方法 2:使用`max() + list comprehension + set() + groupby()`**
以上功能的组合可以用来解决这个特殊的问题。在本文中，我们使用列表理解来执行比较，并使用 max()找到最大元素。

```
# Python3 code to demonstrate working of 
# Consecutive elements maximum frequencies
# Using max() + list comprehension + set() + groupby()
from itertools import groupby

# initializing list
test_list = [5, 6, 7, 7, 6, 6, 5, 7]

# printing original list
print("The original list is : " + str(test_list))

# Consecutive elements maximum frequencies
# Using max() + list comprehension + set() + groupby()
temp = list(set(test_list))
res = [{ele : max([len(list(val)) for key, val in groupby(test_list)
                                  if ele == key])} for ele in temp]

# printing result 
print("The maximum frequencies : " + str(res)) 
```

**Output :**

```
The original list is : [5, 6, 7, 7, 6, 6, 5, 7]
The maximum frequencies : [{5: 1}, {6: 2}, {7: 2}]

```