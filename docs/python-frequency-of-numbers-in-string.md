# Python |字符串中数字的出现频率

> 原文:[https://www . geesforgeks . org/python-字符串中数字的频率/](https://www.geeksforgeeks.org/python-frequency-of-numbers-in-string/)

有时，在处理字符串时，我们会遇到一个问题，需要检查字符串中有多少数字。这是一个常见的问题，在许多领域都有应用，比如日常编程和数据科学。让我们讨论执行这项任务的某些方法。

**方法#1:使用`re.findall() + len()`**
上述功能的组合可用于执行该任务。在这种情况下，我们检查所有的数字，并使用 findall()放入列表中，使用 len()提取计数。

```
# Python3 code to demonstrate working of 
# Frequency of numbers in String
# Using re.findall() + len()
import re

# initializing string
test_str = "geeks4feeks is No. 1 4 geeks"

# printing original string
print("The original string is : " + test_str)

# Frequency of numbers in String
# Using re.findall() + len()
res = len(re.findall(r'\d+', test_str))

# printing result 
print("Count of numerics in string : " + str(res)) 
```

**Output :**

```
The original string is : geeks4feeks is No. 1 4 geeks
Count of numerics in string : 3

```