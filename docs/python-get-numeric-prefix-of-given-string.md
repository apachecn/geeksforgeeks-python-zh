# Python |获取给定字符串的数字前缀

> 原文:[https://www . geesforgeks . org/python-get-numeric-prefix-of-given-string/](https://www.geeksforgeeks.org/python-get-numeric-prefix-of-given-string/)

有时，在处理字符串时，我们可能会遇到需要获取字符串的数字前缀的情况。这种应用程序可以出现在各种领域，例如 web 应用程序开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用`re.findall()`**
正则表达式可以用来执行这个特定的任务。在这种情况下，我们使用 findall 函数来获取数字的所有出现，然后返回初始出现。

```
# Python3 code to demonstrate working of
# Get numeric prefix of string 
# Using re.findall()
import re

# initializing string 
test_str = "1234Geeks"

# printing original string 
print("The original string is : " + test_str)

# Using re.findall()
# Get numeric prefix of string 
res = re.findall('\d+', test_str)

# printing result 
print("The prefix number at string : " + str(res[0]))
```

**Output :**

```
The original string is : 1234Geeks
The prefix number at string : 1234

```