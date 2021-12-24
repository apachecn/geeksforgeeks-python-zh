# Python |列表中连续元素分组

> 原文:[https://www . geesforgeks . org/python-连续元素-列表中分组/](https://www.geeksforgeeks.org/python-consecutive-elements-grouping-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们可能需要根据列表元素各自的连续性对它们进行分组。这种问题可能在数据处理时发生。让我们讨论一下执行这项任务的具体方法。

**方法:使用`enumerate() + groupby()` +生成器函数+ lambda**
该任务可以使用上述函数的组合来执行。在本文中，我们创建了一个生成器函数，其中我们传递了使用`enumerate()`访问其索引元素的列表，并使用`groupby()`和λ按连续元素分组。仅适用于 Python2

```py
# Python code to demonstrate working of
# Consecutive elements grouping list
# using enumerate() + groupby() + generator function + lambda
import itertools

# Utility Generator Function
def groupc(test_list):
    for x, y in itertools.groupby(enumerate(test_list), lambda (a, b): b - a):
        y = list(y)
        yield y[0][1], y[-1][1]

# initialize list
test_list = [1, 2, 3, 6, 7, 8, 11, 12, 13]

# printing original list
print("The original list is : " + str(test_list))

# Consecutive elements grouping list
# using enumerate() + groupby() + generator function + lambda
res = list(groupc(test_list))

# printing result
print("Grouped list is : " + str(res))
```

**Output :**

```py
The original list is : [1, 2, 3, 6, 7, 8, 11, 12, 13]
Grouped list is : [(1, 3), (6, 8), (11, 13)]

```