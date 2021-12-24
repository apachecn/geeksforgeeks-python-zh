# Python–将浮点数转换为数字列表

> 原文:[https://www . geesforgeks . org/python-convert-float-to-digital-list/](https://www.geeksforgeeks.org/python-convert-float-to-digit-list/)

有时，在处理 Python 数据时，我们可能会遇到一个问题，需要将一个浮点数转换为一个数字列表。这个问题在日常编程中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `isdigit()`**
以上功能的组合可以用来执行这个任务。在这种情况下，我们首先将浮点数转换为字符串，然后迭代它，将每个数字转换为整数，并使用列表理解构建列表。

```
# Python3 code to demonstrate working of
# Convert Float to digit list
# using  list comprehension + isdigit()

# initialize N 
N = 6.456

# printing N 
print("The floating number is : " + str(N))

# Convert Float to digit list
# using  list comprehension + isdigit()
res = [int(ele) for ele in str(N) if ele.isdigit()]

# printing result
print("List of floating numbers is : " + str(res))
```

**Output :**

```
The floating number is : 6.456
List of floating numbers is : [6, 4, 5, 6]

```