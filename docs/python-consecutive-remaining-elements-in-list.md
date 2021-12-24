# Python |列表中连续的剩余元素

> 原文:[https://www . geeksforgeeks . org/python-连续-列表中剩余元素/](https://www.geeksforgeeks.org/python-consecutive-remaining-elements-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要获取剩余的连续元素计数(包括当前的)，以便事先做出某些决定。这可能是许多竞争性编程竞赛的潜在子问题。让我们讨论一种可以用来解决这个问题的速记方法。

**方法:使用`range() + from_iterable() + groupby() + list comprehension`**
结合以上功能即可执行并求解该任务。在这种情况下，我们首先使用 groupby 函数来形成组，并使用 `range()`将其转换为反向范围。所有这些都被转换为生成器，以避免创建嵌套列表，然后使用`from_iterable()`获得最终列表。

```
# Python3 code to demonstrate working of
# Consecutive remaining elements in list
# using range() + from_iterable() + groupby() + list comprehension
from itertools import chain, groupby

# initialize list
test_list = [4, 4, 5, 5, 5, 1, 1, 2, 4]

# printing original list
print("The original list is : " + str(test_list))

# Consecutive remaining elements in list
# using range() + from_iterable() + groupby() + list comprehension
temp = (range(len(list(j)), 0, -1) for i, j in groupby(test_list))
res = list(chain.from_iterable(temp))

# printing result
print("Consecutive remaining elements list : " + str(res))
```

**Output :**

```
The original list is : [4, 4, 5, 5, 5, 1, 1, 2, 4]
Consecutive remaining elements list : [2, 1, 3, 2, 1, 2, 1, 1, 1]

```