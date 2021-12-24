# Python |首字母索引

> 原文:[https://www.geeksforgeeks.org/python-first-alphabet-index/](https://www.geeksforgeeks.org/python-first-alphabet-index/)

有时，在使用 Python 字符串时，我们会遇到一个问题，需要从字符串中提取字母字符的第一个索引。这可以在日常编程中应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + regex**
上述功能的组合可用于执行该任务。在这种情况下，我们使用循环来循环字符串，正则表达式用于过滤字符中的字母。

```
# Python3 code to demonstrate working of 
# First alphabet index
# Using loop + regex
import re

# initializing string
test_str = "34#$g67fg"

# printing original string
print("The original string is : " + test_str)

# First alphabet index
# Using loop + regex
res = None
temp = re.search(r'[a-z]', test_str, re.I)
if temp is not None:
    res = temp.start()

# printing result 
print("Index of first character : " + str(res)) 
```

**Output :**

```
The original string is : 34#$g67fg
Index of first character : 4

```