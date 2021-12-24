# Python |查找元组对之间的最大差异

> 原文:[https://www . geesforgeks . org/python-find-元组对之间的最大差异/](https://www.geeksforgeeks.org/python-find-maximum-difference-between-tuple-pairs/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要找到列表中可用对之间的最大差异。这可以应用于数学领域的许多问题。让我们讨论执行这项任务的某些方法。
**方法#1:使用 max() +列表理解**
这个功能的组合可以用来执行这个任务。在本文中，我们计算所有对的绝对差，然后使用 max()返回它的最大值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum difference tuple pair
# Using list comprehension + max()

# initialize list
test_list = [(3, 5), (1, 7), (10, 3), (1, 2)]

# printing original list
print("The original list : " + str(test_list))

# Maximum difference tuple pair
# Using list comprehension + max()
temp = [abs(b - a) for a, b in test_list]
res = max(temp)

# printing result
print("Maximum difference among pairs : " + str(res))
```

**Output : **

```py
The original list : [(3, 5), (1, 7), (10, 3), (1, 2)]
Maximum difference among pairs : 7
```

**方法 2:使用 max() + lambda**
这个和上面的方法差不多。在这种情况下，由列表理解执行的任务使用 lambda 函数来解决，提供了差异计算逻辑。返回最大值。差异对。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum difference tuple pair
# Using lambda + max()

# initialize list
test_list = [(3, 5), (1, 7), (10, 3), (1, 2)]

# printing original list
print("The original list : " + str(test_list))

# Maximum difference tuple pair
# Using lambda + max()
res = max(test_list, key = lambda sub: abs(sub[1] - sub[0]))

# printing result
print("Maximum difference among pairs : " + str(res))
```

**Output : **

```py
The original list : [(3, 5), (1, 7), (10, 3), (1, 2)]
Maximum difference among pairs : (10, 3)
```