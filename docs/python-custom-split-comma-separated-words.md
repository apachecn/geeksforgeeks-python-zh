# Python–自定义拆分逗号分隔单词

> 原文:[https://www . geesforgeks . org/python-custom-split-逗号分隔-word/](https://www.geeksforgeeks.org/python-custom-split-comma-separated-words/)

在使用 Python 时，我们可能会遇到这样的问题，即我们需要执行在空格上拆分字符串单词的任务。但是有时候，我们可以用逗号分隔单词，用逗号连接单词，并要求分开它们。让我们讨论执行这项任务的某些方法。
**方法#1:使用 replace()**
使用 replace()是解决这个问题的一种方法。在这种情况下，我们只需将连接的逗号从字符串分隔成空格，这样它们就可以与其他单词一起正确拆分。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Custom Split Comma Separated Words
# Using replace()

# initializing string
test_str = 'geeksforgeeks, is, best, for, geeks'

# printing original string
print("The original string is : " + str(test_str))

# Distance between occurrences
# Using replace()
res = test_str.replace(", ", " , ").split()

# printing result
print("The strings after performing splits : " + str(res))
```

**Output : **

原来的字符串是:极客 forgeeks，is，best，for，geeks
执行拆分后的字符串:['geeksforgeeks '，'，'，' is '，'，' best '，'，' for '，'，'，' geeks']

**方法 2:使用 re.findall()**
这个问题也可以使用 regex。在这种情况下，我们找到非空格单词的出现，并在此基础上执行拆分。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Custom Split Comma Separated Words
# Using re.findall()
import re

# initializing string
test_str = 'geeksforgeeks, is, best, for, geeks'

# printing original string
print("The original string is : " + str(test_str))

# Distance between occurrences
# Using re.findall()
res = re.findall(r'\w+|\S', test_str)

# printing result
print("The strings after performing splits : " + str(res))
```

**Output : **

原来的字符串是:极客 forgeeks，is，best，for，geeks
执行拆分后的字符串:['geeksforgeeks '，'，'，' is '，'，' best '，'，' for '，'，'，' geeks']