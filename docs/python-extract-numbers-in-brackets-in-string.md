# Python |提取字符串中括号内的数字

> 原文:[https://www . geesforgeks . org/python-extract-括号中的数字-字符串/](https://www.geeksforgeeks.org/python-extract-numbers-in-brackets-in-string/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们必须执行提取括号中的字符串中的数字的任务。让我们讨论执行这项任务的特定方式。

**方法:使用正则表达式**
解决这个任务的方法是构造一个正则表达式字符串，它可以返回字符串中所有有括号的数字。

```py
# Python3 code to demonstrate working of 
# Extract Numbers in Brackets in String
# Using regex
import re

# initializing string
test_str = "gfg is [1] [4] all geeks"

# printing original string
print("The original string is : " + test_str)

# Extract Numbers in Brackets in String
# Using regex
res = re.findall(r"\[\s*\+?(-?\d+)\s*\]", test_str)

# printing result 
print("Extracted number list : " + str(res)) 
```

**Output :**

```py
The original string is : gfg is [1] [4] all geeks
Extracted number list : ['1', '4']

```