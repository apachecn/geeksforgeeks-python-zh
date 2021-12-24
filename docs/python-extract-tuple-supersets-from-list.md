# Python–从列表中提取元组超集

> 原文:[https://www . geeksforgeeks . org/python-extract-tuple-superts-from-list/](https://www.geeksforgeeks.org/python-extract-tuple-supersets-from-list/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要提取所有元组，这些元组包含目标元组中的所有元素。这个问题可以在诸如 web 开发等领域得到应用。让我们讨论一下解决这个问题的某些方法。

> **输入** :
> test_list = [(5，6，6)，(4，2，7)，(9，6，5，6)]
> test_tuple = (6，6)
> T5】输出 : [(5，6，6)，(9，6，5，6)]
> 
> **输入** :
> test_list = [(5，6，6)，(4，2，6)，(9，6，5，6)]
> test_tuple = (6)，
> T5】输出 : [(5，6，6)，(4，2，6)，(9，6，5，6)]

**方法:使用`Counter() + list comprehension + all()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 Counter()执行计数任务。all()用于检查所有元素是否构成子集，列表理解用于将所有逻辑绑定在一个块中。

```py
# Python3 code to demonstrate working of 
# Extract tuple supersets from List
# Using all() + list comprehension + Counter
from collections import Counter

# initializing list
test_list = [(5, 6, 8), (4, 2, 7), (9, 6, 5, 6)]

# printing original list
print("The original list is : " + str(test_list))

# initializing tuple
test_tup = (6, 6, 5)

# Extract tuple supersets from List
# Using all() + list comprehension + Counter
res = [sub for sub in test_list if 
       all(Counter(sub)[x] >= Counter(test_tup)[x]
       for x in Counter(test_tup))]

# printing result 
print("The superset tuples : " + str(res)) 
```

**Output :**

```py
The original list is : [(5, 6, 8), (4, 2, 7), (9, 6, 5, 6)]
The superset tuples : [(9, 6, 5, 6)]

```