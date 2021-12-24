# Python |元组间索引最大值

> 原文:[https://www . geesforgeks . org/python-index-元组间最大值/](https://www.geeksforgeeks.org/python-index-maximum-among-tuples/)

有时，在处理记录时，我们可能会遇到一个共同的问题，即最大化一个元组的内容和其他元组的相应索引。这在我们处理元组记录的几乎所有领域中都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`map() + lambda + max()`**
结合以上功能可以为我们解决问题。在本文中，我们使用 lambda 函数和 max()计算最大值，并使用 map()将逻辑扩展到键。

```py
# Python3 code to demonstrate working of
# Index Maximum among Tuples
# using map() + lambda + max()

# initialize tuples 
test_tup1 = (10, 4, 5)
test_tup2 = (2, 5, 18)

# printing original tuples 
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Index Maximum among Tuples
# using map() + lambda + max()
res = tuple(map(lambda i, j: max(i, j), test_tup1, test_tup2))

# printing result
print("Resultant tuple after maximization : " + str(res))
```

**Output :**

```py
The original tuple 1 : (10, 4, 5)
The original tuple 2 : (2, 5, 18)
Resultant tuple after maximization : (10, 5, 18)

```