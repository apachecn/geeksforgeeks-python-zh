# Python–将列表的元组展平为元组

> 原文:[https://www . geesforgeks . org/python-扁平化-元组列表转元组/](https://www.geeksforgeeks.org/python-flatten-tuple-of-list-to-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要对元组进行扁平化，元组的组成元素是列表。这种问题在机器学习等数据领域很常见。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = ([5]，[6]，[3]，[8])
> **输出** : (5，6，3，8)
> 
> **输入** : test_tuple = ([5，7，8])
> **输出** : (5，7，8)

**方法#1:使用`sum() + tuple()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sum()执行展平任务，传递空列表作为其参数。

```py
# Python3 code to demonstrate working of 
# Flatten tuple of List to tuple
# Using sum() + tuple()

# initializing tuple
test_tuple = ([5, 6], [6, 7, 8, 9], [3])

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Flatten tuple of List to tuple
# Using sum() + tuple()
res = tuple(sum(test_tuple, []))

# printing result 
print("The flattened tuple : " + str(res))
```

**Output :**

```py
The original tuple : ([5, 6], [6, 7, 8, 9], [3])
The flattened tuple : (5, 6, 6, 7, 8, 9, 3)

```

**方法 2:使用`tuple() + chain.from_iterable()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 from_iterable()执行展平任务，并使用 tuple()执行到 tuple 的转换。

```py
# Python3 code to demonstrate working of 
# Flatten tuple of List to tuple
# Using tuple() + chain.from_iterable()
from itertools import chain

# initializing tuple
test_tuple = ([5, 6], [6, 7, 8, 9], [3])

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Flatten tuple of List to tuple
# Using tuple() + chain.from_iterable()
res = tuple(chain.from_iterable(test_tuple))

# printing result 
print("The flattened tuple : " + str(res))
```

**Output :**

```py
The original tuple : ([5, 6], [6, 7, 8, 9], [3])
The flattened tuple : (5, 6, 6, 7, 8, 9, 3)

```