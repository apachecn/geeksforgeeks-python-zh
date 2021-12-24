# Python |检查变量是否为元组

> 原文:[https://www . geesforgeks . org/python-check-if-variable-is-tuple/](https://www.geeksforgeeks.org/python-check-if-variable-is-tuple/)

有时，在使用 Python 时，我们可能会遇到一个问题，需要检查变量是单个还是记录。这在需要限制我们处理的数据类型的领域中有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`type()`**
这个内置的功能可以作为执行这个任务的简写。它检查变量的类型，也可以用来检查元组。

```py
# Python3 code to demonstrate working of
# Check if variable is tuple
# using type()

# initialize tuple 
test_tup = (4, 5, 6)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Check if variable is tuple
# using type()
res = type(test_tup) is tuple

# printing result
print("Is variable tuple ? : " + str(res))
```

**Output :**

```py
The original tuple : (4, 5, 6)
Is variable tuple ? : True

```