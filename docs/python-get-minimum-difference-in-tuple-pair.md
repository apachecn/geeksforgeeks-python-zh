# Python–获取元组对中的最小差异

> 原文:[https://www . geesforgeks . org/python-get-最小元组对差异/](https://www.geeksforgeeks.org/python-get-minimum-difference-in-tuple-pair/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要找到列表中可用对之间的最小差异。这可以应用于数学领域的许多问题。让我们讨论执行这项任务的某些方法。
**方法#1:使用 min() +列表理解**
这个功能的组合可以用来执行这个任务。在这种情况下，我们计算所有对的绝对差，然后使用 min()返回它的 min。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Tuple minimum difference in pair
# Using list comprehension + min()

# initialize list
test_list = [(3, 5), (1, 7), (10, 3), (1, 2)]

# printing original list
print("The original list : " + str(test_list))

# Tuple minimum difference in pair
# Using list comprehension + min()
temp = [abs(b - a) for a, b in test_list]
res = min(temp)

# printing result
print("Minimum difference among pairs : " + str(res))
```

**Output : **

```
The original list : [(3, 5), (1, 7), (10, 3), (1, 2)]
Minimum difference among pairs : 1
```

**方法 2:使用 min() + lambda**
这个和上面的方法差不多。在这种情况下，由列表理解执行的任务使用 lambda 函数来解决，提供了差异计算逻辑。返回最小值。差异对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Tuple minimum difference in pair
# Using lambda + min()

# initialize list
test_list = [(3, 5), (1, 7), (10, 3), (1, 2)]

# printing original list
print("The original list : " + str(test_list))

# Tuple minimum difference in pair
# Using lambda + min()
res = min(test_list, key = lambda sub: abs(sub[1] - sub[0]))

# printing result
print("Minimum difference among pairs : " + str(res))
```

**Output : **

```
The original list : [(3, 5), (1, 7), (10, 3), (1, 2)]
Minimum difference among pairs : (1, 2)
```