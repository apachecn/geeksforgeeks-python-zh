# Python |将元组转换为整数

> 原文:[https://www . geesforgeks . org/python-convert-tuple-to-integer/](https://www.geeksforgeeks.org/python-convert-tuple-to-integer/)

有时，在处理记录时，我们可能会遇到一个问题，即我们需要通过连接数据记录来将它们转换为整数。让我们讨论执行这项任务的某些方法。

**方法#1:使用`reduce()` + lambda**
以上功能的组合可以用来执行此任务。在这种情况下，我们使用 lambda 函数来执行转换逻辑，并减少执行迭代和组合结果的任务。

```py
# Python3 code to demonstrate working of
# Convert Tuple to integer
# Using reduce() + lambda
import functools

# initialize tuple
test_tuple = (1, 4, 5)

# printing original tuple 
print("The original tuple : " + str(test_tuple))

# Convert Tuple to integer
# Using reduce() + lambda
res = functools.reduce(lambda sub, ele: sub * 10 + ele, test_tuple)

# printing result
print("Tuple to integer conversion : " + str(res))
```

**Output :**

```py
The original tuple : (1, 4, 5)
Tuple to integer conversion : 145

```