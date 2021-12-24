# 访问 Python 元组的前后元素

> 原文:[https://www . geesforgeks . org/access-python 前后元素元组/](https://www.geeksforgeeks.org/access-front-and-rear-element-of-python-tuple/)

有时，在处理记录时，我们可能会遇到一个问题，即我们需要访问特定记录的初始和最后数据。这种问题在许多领域都有应用。让我们讨论一些解决这个问题的方法。

**方法#1:使用访问括号**
我们可以使用访问括号执行元组中前后元素的可能获取，方式类似于列表中元素的访问方式。

```
# Python3 code to demonstrate working of
# Accessing front and rear element of tuple
# using access brackets

# initialize tuple
test_tup = (10, 4, 5, 6, 7)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Accessing front and rear element of tuple
# using access brackets
res = (test_tup[0], test_tup[-1])

# printing result
print("The front and rear element of tuple are : " + str(res))
```

**Output :**

```
The original tuple : (10, 4, 5, 6, 7)
The front and rear element of tuple are : (10, 7)

```