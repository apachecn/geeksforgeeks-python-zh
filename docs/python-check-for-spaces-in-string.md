# Python |检查字符串中的空格

> 原文:[https://www . geesforgeks . org/python-检查字符串中的空格/](https://www.geeksforgeeks.org/python-check-for-spaces-in-string/)

有时，我们可能会遇到一个问题，我们需要检查字符串是否有空格。这类问题可以在机器学习领域得到特定类型的数据集。让我们讨论一下解决这类问题的某些方法。

**方法#1:使用正则表达式**
这种问题可以使用 python 提供的正则表达式实用程序来解决。通过在`search()`中输入适当的正则表达式字符串，我们可以检查字符串中是否存在空格。

```
# Python3 code to demonstrate working of
# Check for spaces in string
# Using regex
import re

# initializing string 
test_str = "Geeks  forGeeks"

# printing original string 
print("The original string is : " + test_str)

# Using regex
# Check for spaces 
res = bool(re.search(r"\s", test_str))

# printing result 
print("Does string contain spaces ? " + str(res))
```

**Output :**

```
The original string is : Geeks  forGeeks
Does string contain spaces ? True

```

**方法 2:使用`in`运算符**
该任务也可以使用 in 运算符执行。只需要检查字符串中的空格。即使找到一个空格，返回的结果也是真的，否则就是假的。

```
# Python3 code to demonstrate working of
# Check for spaces in string
# Using in operator

# initializing string 
test_str = "Geeks  forGeeks"

# printing original string 
print("The original string is : " + test_str)

# Using in operator
# Check for spaces 
res = " " in test_str

# printing result 
print("Does string contain spaces ? " + str(res))
```

**Output :**

```
The original string is : Geeks  forGeeks
Does string contain spaces ? True

```