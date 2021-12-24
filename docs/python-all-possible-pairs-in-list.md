# Python–列表中所有可能的对

> 原文:[https://www . geesforgeks . org/python-所有可能的列表对/](https://www.geeksforgeeks.org/python-all-possible-pairs-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要从列表中的整数中提取所有可能执行的对。这种问题可能发生在许多领域，例如日常编程和 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [1，7，4]
> **输出** : [(1，7)，(1，4)，(7，4)]
> 
> **输入** : test_list = [7，4]
> **输出** : [(7，4)]

**方法#1:使用列表理解+ `enumerate()`**
这是可以执行此任务的方式之一。在本文中，我们使用列表理解方法中的嵌套循环来执行配对任务，并在迭代时使用 enumerate()来检查下一个索引。

```py
# Python3 code to demonstrate working of 
# All possible pairs in List
# Using list comprehension + enumerate()

# initializing list
test_list = [1, 7, 4, 3]

# printing original list 
print("The original list : " + str(test_list))

# All possible pairs in List
# Using list comprehension + enumerate()
res = [(a, b) for idx, a in enumerate(test_list) for b in test_list[idx + 1:]]

# printing result 
print("All possible pairs : " + str(res))
```

**Output :**

```py
The original list : [1, 7, 4, 3]
All possible pairs : [(1, 7), (1, 4), (1, 3), (7, 4), (7, 3), (4, 3)]

```

**方法 2:使用`combinations()`**
这是可以执行此任务的方式之一。在这种情况下，我们只是使用 inbuild 函数进行配对，并发送 2 作为大小为 2 的配对的值。

```py
# Python3 code to demonstrate working of 
# All possible pairs in List
# Using combinations()
from itertools import combinations

# initializing list
test_list = [1, 7, 4, 3]

# printing original list 
print("The original list : " + str(test_list))

# All possible pairs in List
# Using combinations()
res = list(combinations(test_list, 2))

# printing result 
print("All possible pairs : " + str(res))
```

**Output :**

```py
The original list : [1, 7, 4, 3]
All possible pairs : [(1, 7), (1, 4), (1, 3), (7, 4), (7, 3), (4, 3)]

```