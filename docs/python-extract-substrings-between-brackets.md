# Python |提取括号之间的子字符串

> 原文:[https://www . geeksforgeeks . org/python-extract-substrings-括号间/](https://www.geeksforgeeks.org/python-extract-substrings-between-brackets/)

有时，在使用 Python 字符串时，我们会遇到一个问题，即我们需要提取某些字符之间的子字符串，这些子字符串可以是括号。在我们将元组嵌入字符串的情况下，这可能会有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用正则表达式**
解决这个问题的一种方法是使用正则表达式。在这种情况下，我们使用合适的正则表达式并执行提取所需元素的任务。

```py
# Python3 code to demonstrate working of 
# Extract substrings between brackets
# Using regex
import re

# initializing string
test_str = "geeks(for)geeks is (best)"

# printing original string
print("The original string is : " + test_str)

# Extract substrings between brackets
# Using regex
res = re.findall(r'\(.*?\)', test_str)

# printing result 
print("The element between brackets : " + str(res)) 
```

**Output :**

```py
The original string is : geeks(for)geeks is (best)
The element between brackets : ['(for)', '(best)']

```