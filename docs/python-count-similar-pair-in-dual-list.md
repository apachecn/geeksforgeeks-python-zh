# Python–在双列表中计数相似对

> 原文:[https://www . geesforgeks . org/python-count-like-in-pair-in-double-list/](https://www.geeksforgeeks.org/python-count-similar-pair-in-dual-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们接收到双元素对，我们打算找到相似元素对及其频率。这种数据通常在数据域中很有用。让我们讨论执行这项任务的某些方法。
**方法#1:使用 Counter()+map()+sorted()+items()**
以上功能的组合可以用来实现这个特定的任务。在本文中，我们首先使用 Counter 找到频率，然后使用 map()将其链接到元组中。sorted()在使用上述方法之前执行排序任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Count Similar pair in dual list
# using Counter() + map() + sorted() + items()
from collections import Counter

# initializing list
test_list = [[1, 2], [2, 1], [3, 4], [4, 3], [5, 4]]

# printing original list
print ("The original list is : " + str(test_list))

# Count Similar pair in dual list
# using Counter() + map() + sorted() + items()
temp = [sorted(ele) for ele in test_list]
res = [(i, j, k) for (i, j), k in Counter(map(tuple, temp)).items()]

# printing result
print ("The dual list similarity counts : " + str(res))
```

**Output : **

```py
The original list is : [[1, 2], [2, 1], [3, 4], [4, 3], [5, 4]]
The dual list similarity counts : [(1, 2, 2), (4, 5, 1), (3, 4, 2)]
```

**方法 2:使用 sum() +列表理解+ groupby() + sorted()**
在该方法中，使用 sum()执行计数任务，使用 groupby()执行获取组的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Count Similar pair in dual list
# using sum() + list comprehension + groupby() + sorted()
from itertools import groupby

# initializing list
test_list = [[1, 2], [2, 1], [3, 4], [4, 3], [5, 4]]

# printing original list
print ("The original list is : " + str(test_list))

# Count Similar pair in dual list
# using sum() + list comprehension + groupby() + sorted()
res = [(*temp, sum(1 for idx in elements))
      for temp, elements in groupby(test_list, key = lambda j : sorted(j))]

# printing result
print ("The dual list similarity counts : " + str(res))
```

**Output : **

```py
The original list is : [[1, 2], [2, 1], [3, 4], [4, 3], [5, 4]]
The dual list similarity counts : [(1, 2, 2), (4, 5, 1), (3, 4, 2)]
```