# Python–将蛇的大小写转换为帕斯卡大小写

> 原文:[https://www . geesforgeks . org/python-convert-snake-case-to-Pascal-case/](https://www.geeksforgeeks.org/python-convert-snake-case-to-pascal-case/)

有时，在使用 Python 字符串时，我们会遇到需要执行字符串大小写转换的问题。这是一个很常见的问题。这在许多领域都有应用，比如 web 开发。让我们讨论执行这项任务的某些方法。

> 输入:极客 _ for _ 极客
> 输出:极客 forGeeks
> 
> 输入:left_index
> 输出:leftIndex

**方法#1:使用`title() + replace()`**
这个任务可以使用以上功能的组合来解决。在这种情况下，我们首先将下划线转换为空字符串，然后给每个单词加上标题大小写。

```py
# Python3 code to demonstrate working of 
# Convert Snake case to Pascal case
# Using title() + replace()

# initializing string
test_str = 'geeksforgeeks_is_best'

# printing original string
print("The original string is : " + test_str)

# Convert Snake case to Pascal case
# Using title() + replace()
res = test_str.replace("_", " ").title().replace(" ", "")

# printing result 
print("The String after changing case : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeks_is_best
The String after changing case : GeeksforgeeksIsBest

```

**方法 2:使用`capwords()`**
执行标题案例的任务在该方法中使用 capwords()执行。

```py
# Python3 code to demonstrate working of 
# Convert Snake case to Pascal case
# Using capwords()
import string

# initializing string
test_str = 'geeksforgeeks_is_best'

# printing original string
print("The original string is : " + test_str)

# Convert Snake case to Pascal case
# Using capwords()
res = string.capwords(test_str.replace("_", " ")).replace(" ", "")

# printing result 
print("The String after changing case : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeks_is_best
The String after changing case : GeeksforgeeksIsBest

```