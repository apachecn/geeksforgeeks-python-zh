# Python |检查一个元组是否是其他元组的子集

> 原文:[https://www . geesforgeks . org/python-检查一元组是否是其他的子集/](https://www.geeksforgeeks.org/python-check-if-one-tuple-is-subset-of-other/)

有时，在使用 Python 时，我们可以处理不同的数据，我们可能需要解决检查一个子集是否是另一个子集的一部分的问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用 issubset()**
我们可以使用元组到集合的类型转换来解决这个问题，然后使用 issubset()检查一个元组是否是其他元组的子集。

```py
# Python3 code to demonstrate working of
# Check if one tuple is subset of other
# using issubset()

# initialize tuples
test_tup1 = (10, 4, 5, 6)
test_tup2 = (5, 10)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Check if one tuple is subset of other
# using issubset()
res = set(test_tup2).issubset(test_tup1)

# printing result
print("Is 2nd tuple subset of 1st ? : " + str(res))
```

**Output :**

```py
The original tuple 1 : (10, 4, 5, 6)
The original tuple 2 : (5, 10)
Is 2nd tuple subset of 1st ? : True

```