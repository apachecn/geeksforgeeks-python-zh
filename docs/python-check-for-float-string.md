# Python |检查浮动字符串

> 原文:[https://www . geesforgeks . org/python-check-for-float-string/](https://www.geeksforgeeks.org/python-check-for-float-string/)

Python 带来的最显著的突破之一是数据类型之间的相互转换是以非常简单的方式完成的，因此使它非常强大。字符串可以很容易地转换成整数，但是转换浮点值仍然是一项困难的任务。让我们讨论一些可以检查字符串是否为浮点数的方法，以避免潜在的错误。

**方法#1:使用`isdigit() + replace()`**
上述功能的组合用于执行该任务，因此。这分两步进行，首先删除点值，将字符串连接成一个数字，然后进行检查。缺点是它没有检查潜在的指数值，这些指数值也可以形成浮点数。

```py
# Python3 code to demonstrate
# Check for float string
# using isdigit() + replace()

# initializing string 
test_string = "45.657"

# printing original string 
print("The original string : " + str(test_string))

# using isdigit() + replace()
# Check for float string
res = test_string.replace('.', '', 1).isdigit()

# print result
print("Is string a possible float number ? : " + str(res))
```

**Output :**

```py
The original string : 45.657
Is string a possible float number ? : True

```