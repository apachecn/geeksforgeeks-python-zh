# Python–将元组转换为元组对

> 原文:[https://www . geesforgeks . org/python-convert-tuple-to-tuple-pair/](https://www.geeksforgeeks.org/python-convert-tuple-to-tuple-pair/)

有时，在处理 Python Tuple 记录时，我们可能会遇到一个问题，即我们需要将具有 3 个元素的单元组转换为双元组对。这是一个相当特殊的问题，但在日常编程和竞争性编程中可能会有问题。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = ('A '，' B '，' C')
> **输出** : [('A '，' B '，(' A '，' C')]
> 
> **输入** : test_tuple = ('X '，' Y '，' Z')
> **输出** : [('X '，' Y ')，(' X '，' Z')]

**方法#1:使用`product() + next()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 product 进行配对，使用 nex()进行与下一个元素配对的选择。

```py
# Python3 code to demonstrate working of 
# Convert Tuple to Tuple Pair
# Using product() + next()
from itertools import product

# initializing tuple
test_tuple = ('G', 'F', 'G')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Convert Tuple to Tuple Pair
# Using product() + next()
test_tuple = iter(test_tuple)
res = list(product(next(test_tuple), test_tuple))

# printing result 
print("The paired records : " + str(res))
```

**Output :**

```py
The original tuple : ('G', 'F', 'G')
The paired records : [('G', 'F'), ('G', 'G')]

```

**方法 2:使用`repeat() + zip() + next()`**
这个问题也可以通过以上功能的组合来解决。在本例中，我们使用 zip()执行配对任务，使用 repeat()执行重复任务。

```py
# Python3 code to demonstrate working of 
# Convert Tuple to Tuple Pair
# Using repeat() + zip() + next()
from itertools import repeat

# initializing tuple
test_tuple = ('G', 'F', 'G')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Convert Tuple to Tuple Pair
# Using repeat() + zip() + next()
test_tuple = iter(test_tuple)
res = list(zip(repeat(next(test_tuple)), test_tuple))

# printing result 
print("The paired records : " + str(res))
```

**Output :**

```py
The original tuple : ('G', 'F', 'G')
The paired records : [('G', 'F'), ('G', 'G')]

```