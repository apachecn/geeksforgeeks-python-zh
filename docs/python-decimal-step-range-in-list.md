# Python |列表中的十进制步长范围

> 原文:[https://www . geeksforgeeks . org/python-十进制步长范围列表/](https://www.geeksforgeeks.org/python-decimal-step-range-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要在一个十进制范围内填充列表。使用内置构造更容易处理整数范围，但是使用十进制值来提供范围值是行不通的。让我们讨论一下解决这个问题的方法。

**方法:使用列表理解**
解决这个问题的一种方法是使用列表理解，通过迭代列表并将范围元素乘以元素的索引，可以更容易地解决这个问题。

```py
# Python3 code to demonstrate working of
# Decimal step range in list
# using list comprehension

# initializing start value 
strt = 5

# initializing step value 
step = 0.4

# using list comprehension
# Decimal step range 
test_list = [strt + (x * step) for x in range(0, 5)]

# Printing result
print("The list after decimal range value initialization : " + str(test_list))
```

**Output :**

```py

The list after decimal range value initialization : [5.0, 5.4, 5.8, 6.2, 6.6]

```