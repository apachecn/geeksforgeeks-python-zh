# Python–元组之间的“与”运算

> 原文:[https://www . geesforgeks . org/python-and-operation-with-tuples/](https://www.geeksforgeeks.org/python-and-operation-between-tuples/)

有时，在处理记录时，我们可能会遇到一个常见的问题，那就是对一个元组的内容和另一个元组的相应索引执行“与”运算。这在我们处理元组记录的几乎所有领域中都有应用，尤其是数据科学。让我们讨论执行这项任务的某些方法。

**方法一:使用`map()` + lambda**
结合以上功能可以为我们解决问题。在本文中，我们使用 lambda 函数计算 AND，并使用 map()将逻辑扩展到键。

```py
# Python3 code to demonstrate working of
# Cross Tuple AND operation
# using map() + lambda

# initialize tuples 
test_tup1 = (10, 4, 5)
test_tup2 = (2, 5, 18)

# printing original tuples 
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Cross Tuple AND operation
# using map() + lambda
res = tuple(map(lambda i, j: i & j, test_tup1, test_tup2))

# printing result
print("Resultant tuple after AND operation : " + str(res))
```

**Output :**

```py
The original tuple 1 : (10, 4, 5)
The original tuple 2 : (2, 5, 18)
Resultant tuple after AND operation : (2, 4, 0)

```