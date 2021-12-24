# Python |元组列表中的累计索引求和

> 原文:[https://www . geesforgeks . org/python-累积-索引-元组列表中的求和/](https://www.geeksforgeeks.org/python-accumulative-index-summation-in-tuple-list/)

有时，在处理数据时，我们会遇到一个问题，即我们需要找到元组中每个索引的累积总和。这个问题可以应用于 web 开发和竞争性编程领域。让我们讨论一下解决这个问题的某些方法。

**方法:使用`accumulate() + sum() + lambda + map() + tuple() + zip()`**
以上功能的组合可以用来解决这个任务。在本例中，我们使用`zip()`对元素进行配对，然后计算它们的总和，并使用`map()`将其扩展到所有元素。求和是通过累加来实现的。所有逻辑的绑定都是由 lambda 函数完成的。

```py
# Python3 code to demonstrate working of
# Accumulative index summation in tuple list
# Using accumulate() + sum() + lambda + map() + tuple() + zip()
from itertools import accumulate

# initialize list
test_list = [(3, 4, 5), (4, 5, 7), (1, 4, 10)]

# printing original list 
print("The original list : " + str(test_list))

# Accumulative index summation in tuple list
# Using accumulate() + sum() + lambda + map() + tuple() + zip()
res = list(accumulate(test_list, lambda i, j: tuple(map(sum, zip(i, j)))))

# printing result
print("Accumulative index summation of tuple list : " + str(res))
```

**Output :**

```py
The original list : [(3, 4, 5), (4, 5, 7), (1, 4, 10)]
Accumulative index summation of tuple list : [(3, 4, 5), (7, 9, 12), (8, 13, 22)]

```