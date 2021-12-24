# Python |用空字典初始化列表

> 原文:[https://www . geesforgeks . org/python-initialize-list-with-empty-dictionary/](https://www.geeksforgeeks.org/python-initialize-list-with-empty-dictionaries/)

在使用 Python 时，我们可能会遇到一个问题，那就是我们需要用空字典初始化一个特定大小的列表。这个任务在 web 开发中存储记录很有用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`{} + "*" operator`**
该任务可以使用“*”运算符执行。我们可以创建一个包含单个空字典的列表，然后将其乘以列表大小的数字。缺点是将制作指向相似存储位置的相似参考字典。

```py
# Python3 code to demonstrate working of
# Initialize list with empty dictionaries
# using {} + "*" operator

# Initialize list with empty dictionaries
# using {} + "*" operator
res = [{}] * 6

print("The list of empty dictionaries is : " + str(res))
```

**Output :**

```py
The list of empty dictionaries is : [{}, {}, {}, {}, {}, {}]

```