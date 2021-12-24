# Python |如何获取元组减法

> 原文:[https://www . geesforgeks . org/python-如何获得元组减法/](https://www.geeksforgeeks.org/python-how-to-get-subtraction-of-tuples/)

有时，在处理记录时，我们可能会遇到一个常见的问题:用其他元组的相应索引减去一个元组的内容。这在我们处理元组记录的几乎所有领域中都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用 `map()` + lambda**
结合以上功能可以为我们解决问题。在本文中，我们使用 lambda 函数计算减法，并使用 map()将逻辑扩展到键。

```
# Python3 code to demonstrate working of
# Subtraction of tuples
# using map() + lambda

# initialize tuples 
test_tup1 = (10, 4, 5)
test_tup2 = (2, 5, 18)

# printing original tuples 
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Subtraction of tuples
# using map() + lambda
res = tuple(map(lambda i, j: i - j, test_tup1, test_tup2))

# printing result
print("Resultant tuple after subtraction : " + str(res))
```

**Output :**

```
The original tuple 1 : (10, 4, 5)
The original tuple 2 : (2, 5, 18)
Resultant tuple after subtraction : (8, -1, -13)

```