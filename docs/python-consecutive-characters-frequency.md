# Python |连续字符频率

> 原文:[https://www . geesforgeks . org/python-连续字符-频率/](https://www.geeksforgeeks.org/python-consecutive-characters-frequency/)

有时，在使用 Python 时，我们会遇到一个问题，即我们需要计算连续字符的频率，直到字符发生变化。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `groupby()`**
这是一种速记方式，借助于它可以完成这项任务。在这种情况下，我们使用 groupby()将连续的序列组合在一起进行频率计算。

```py
# Python3 code to demonstrate working of 
# Consecutive characters frequency
# Using list comprehension + groupby()
from itertools import groupby

# initializing string
test_str = "geekksforgggeeks"

# printing original string
print("The original string is : " + test_str)

# Consecutive characters frequency
# Using list comprehension + groupby()
res = [len(list(j)) for _, j in groupby(test_str)]

# printing result 
print("The Consecutive characters frequency : " + str(res)) 
```

**Output :**

```py
The original string is : geekksforgggeeks
The Consecutive characters frequency : [1, 2, 2, 1, 1, 1, 1, 3, 2, 1, 1]

```