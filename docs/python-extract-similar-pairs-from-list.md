# Python–从列表中提取相似对

> 原文:[https://www . geesforgeks . org/python-extract-like-pairs-from-list/](https://www.geeksforgeeks.org/python-extract-similar-pairs-from-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，需要提取列表中的所有元素对。这种问题可以应用于诸如 web 开发和日常编程等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [1，2，3，4]
> **输出** : []
> 
> **输入** : test_list = [2，2，2，2，3，3，4]
> **输出** : [(2，2)，(2，2)，(3，3)]

**方法一:使用`Counter()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，使用 Counter()提取频率，并使用列表理解完成对构造。

```
# Python3 code to demonstrate working of 
# Extract Similar pairs from List
# Using Counter() + list comprehension
from collections import Counter

# initializing list
test_list = [4, 6, 7, 4, 2, 6, 2, 8]

# printing original list
print("The original list is : " + str(test_list))

# Extract Similar pairs from List
# Using Counter() + list comprehension
res = [(key, key) for key, val in Counter(test_list).items() 
                                  for _ in range(val // 2)]

# printing result 
print("The records after pairing : " + str(res)) 
```

**Output :**

```
The original list is : [4, 6, 7, 4, 2, 6, 2, 8]
The records after pairing : [(4, 4), (6, 6), (2, 2)]

```

**方法 2:使用`fromkeys()` +列表理解**
这是执行这个任务的又一种方式。在本例中，我们使用字典的 fromkeys()和 get()执行 Counter()任务，即获取频率。

```
# Python3 code to demonstrate working of 
# Extract Similar pairs from List
# Using fromkeys() + list comprehension

# initializing list
test_list = [4, 6, 7, 4, 2, 6, 2, 8]

# printing original list
print("The original list is : " + str(test_list))

# Extract Similar pairs from List
# Using fromkeys() + list comprehension
temp = dict.fromkeys(test_list, 0)
for key in test_list:
    temp[key] += 1
res = [(key, key) for key, val in temp.items() for _ in range(val // 2)]

# printing result 
print("The records after pairing : " + str(res)) 
```

**Output :**

```
The original list is : [4, 6, 7, 4, 2, 6, 2, 8]
The records after pairing : [(4, 4), (6, 6), (2, 2)]

```