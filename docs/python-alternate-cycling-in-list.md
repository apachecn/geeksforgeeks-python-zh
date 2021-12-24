# Python |列表中的交替循环

> 原文:[https://www . geesforgeks . org/python-alternate-cycling-in-list/](https://www.geeksforgeeks.org/python-alternate-cycling-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要以不同的方式执行列表的访问/打印。在一些变体中，可能需要以交替循环的方式打印列表，即从前面打印元素并交替读取。这是一个流行的校内编程问题。让我们讨论一下执行这项任务的特定方式。

**方法:使用`reversed() + islice() + iter() + cycle() + next()` +列表理解**
上述功能的组合可用于执行该任务。在这种情况下，`reversed() and iter()`分别用于创建反向和正常序列列表的迭代器，`cycle()` 执行交替访问的任务。`islice()`执行提取元素和构建新列表的任务。 `next()`执行访问元素的任务。

**代码:**

```
# Python3 code to demonstrate working of
# Alternate Cycling in list
# using reversed() + islice() + iter() + cycle() + next() + list comprehension
from itertools import islice, cycle

# initialize list
test_list = [5, 6, 8, 9, 10, 21, 3]

# printing original list
print("The original list is : " + str(test_list))

# Alternate Cycling in list
# using reversed() + islice() + iter() + cycle() + next() + list comprehension
res = [next(i) for i in islice(cycle((iter(test_list), 
                                     reversed(test_list))), len(test_list))]

# printing result
print("Alternate Cyclic iteration is : " + str(res))
```

**Output :**

```
The original list is : [5, 6, 8, 9, 10, 21, 3]
Alternate Cyclic iteration is : [5, 3, 6, 21, 8, 10, 9]

```