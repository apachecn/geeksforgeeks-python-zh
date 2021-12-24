# Python–2 元组的所有配对组合

> 原文:[https://www . geeksforgeeks . org/python-全对 2 元组组合/](https://www.geeksforgeeks.org/python-all-pair-combinations-of-2-tuples/)

有时，在处理 Python 元组数据时，我们可能会遇到一个问题，即我们需要提取 2 个参数元组的所有可能组合。这种应用可以出现在数据科学或游戏领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple1 = (7，2)，test_tuple2 = (7，8)
> **输出** : [(7，7)，(7，8)，(2，7)，(2，8)，(7，7)，(7，2)，(8，7)，(7)，(7，7)，(8，7)，(8，8，2)]
> 
> **输入** : test_tuple1 = (9，2)，test_tuple2 = (7，8)
> **输出** : [(9，7)，(9，8)，(2，7)，(2，8)，(7，9)，(7，2)，(8，9)，(8，9)，(8，8，2)]

**方法#1:使用列表理解**
这是执行这个任务的方法之一。在这种情况下，我们执行的任务是在一个过程中形成一个索引组合，在另一个过程中更改索引，并添加到初始结果列表中。

```py
# Python3 code to demonstrate working of 
# All pair combinations of 2 tuples
# Using list comprehension

# initializing tuples
test_tuple1 = (4, 5)
test_tuple2 = (7, 8)

# printing original tuples
print("The original tuple 1 : " + str(test_tuple1))
print("The original tuple 2 : " + str(test_tuple2))

# All pair combinations of 2 tuples
# Using list comprehension
res =  [(a, b) for a in test_tuple1 for b in test_tuple2]
res = res +  [(a, b) for a in test_tuple2 for b in test_tuple1]

# printing result 
print("The filtered tuple : " + str(res))
```

**Output :**

```py
The original tuple 1 : (4, 5)
The original tuple 2 : (7, 8)
The filtered tuple : [(4, 7), (4, 8), (5, 7), (5, 8), (7, 4), (7, 5), (8, 4), (8, 5)]

```

**方法 2:使用`chain() + product()`**
上述功能的组合提供了解决这个问题的另一种方法。在本例中，我们使用 product()执行配对创建任务，chain()用于将两次使用的 product()的结果相加。

```py
# Python3 code to demonstrate working of 
# All pair combinations of 2 tuples
# Using chain() + product()
from itertools import chain, product

# initializing tuples
test_tuple1 = (4, 5)
test_tuple2 = (7, 8)

# printing original tuples
print("The original tuple 1 : " + str(test_tuple1))
print("The original tuple 2 : " + str(test_tuple2))

# All pair combinations of 2 tuples
# Using chain() + product()
res = list(chain(product(test_tuple1, test_tuple2), product(test_tuple2, test_tuple1)))

# printing result 
print("The filtered tuple : " + str(res))
```

**Output :**

```py
The original tuple 1 : (4, 5)
The original tuple 2 : (7, 8)
The filtered tuple : [(4, 7), (4, 8), (5, 7), (5, 8), (7, 4), (7, 5), (8, 4), (8, 5)]

```