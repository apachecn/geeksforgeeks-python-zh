# Python |自定义列表切片求和

> 原文:[https://www . geesforgeks . org/python-custom-list-slicing-sum/](https://www.geeksforgeeks.org/python-custom-list-slicing-sum/)

对一个列表进行切片的问题已经在前面讨论过了，但是有时我们需要根据其他列表中给出的输入来执行可变长度的切片及其求和。这个问题在 web 开发中有潜在的应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`itertools.islice() + sum()` +列表理解**
列表理解可用于遍历列表，组件问题使用 islice 函数解决。求和由 sum()执行。

```py
# Python3 code to demonstrate
# Custom List slicing Sum
# using itertools.islice() + sum() + list comprehension
from itertools import islice

# initializing test list
test_list = [1, 5, 3, 7, 8, 10, 11, 16, 9, 12]

# initializing slice list 
slice_list = [2, 1, 3, 4]

# printing original list 
print("The original list : " + str(test_list))

# printing slice list 
print("The slice list : " + str(slice_list))

# using itertools.islice() + sum() + list comprehension
# Custom List slicing Sum
temp = iter(test_list)
res = [sum(list(islice(temp, part))) for part in slice_list]

# print result
print("The variable sliced sum list is : " + str(res))
```

**Output :**

```py
The original list : [1, 5, 3, 7, 8, 10, 11, 16, 9, 12]
The slice list : [2, 1, 3, 4]
The variable sliced sum list is : [6, 3, 25, 48]

```