# Python |字符串中的案例计数器

> 原文:[https://www . geesforgeks . org/python-case-counter-in-string/](https://www.geeksforgeeks.org/python-case-counter-in-string/)

有时，在使用 Python String 时，我们可能会遇到一个问题，需要区分小写和大写的计数。这种操作可以在许多领域得到应用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用`map() + sum() + isupper() + islower()`**
上述功能的组合可用于执行该任务。在本文中，我们分别使用 sum()和 map()以及各自的内置函数来提取计数。

```py
# Python3 code to demonstrate working of
# Case Counter in String
# using map() + sum() + isupper + islower

# initializing string 
test_str = "GFG is For GeeKs"

# printing original string 
print("The original string is : " + test_str)

# Case Counter in String
# using map() + sum() + isupper + islower
res_upper = sum(map(str.isupper, test_str))
res_lower = sum(map(str.islower, test_str))

# printing result
print("The count of Upper case characters : " + str(res_upper))
print("The count of Lower case characters : " + str(res_lower))
```

**Output :**

```py
The original string is : GFG is For GeeKs
The count of Upper case characters : 6
The count of Lower case characters : 7

```