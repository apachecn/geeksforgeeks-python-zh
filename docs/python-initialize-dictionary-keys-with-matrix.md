# Python–用矩阵初始化字典键

> 原文:[https://www . geesforgeks . org/python-initialize-dictionary-key-with-matrix/](https://www.geeksforgeeks.org/python-initialize-dictionary-keys-with-matrix/)

有时，在使用 Python 数据时，我们会遇到一个问题，即我们需要构建一个空的字典网格来进一步填充数据。这个问题在许多领域都有应用，包括数据操作。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解**
这是可以执行这个任务的方式之一。在本文中，我们通过使用列表理解进行迭代，用空网格初始化字典键。

```
# Python3 code to demonstrate working of 
# Initialize dictionary keys with Matrix
# Using list comprehension

# initializing N
num = 4

# Initialize dictionary keys with Matrix
# Using list comprehension
res = {'gfg': [[] for _ in range(num)], 'best': [[] for _ in range(num)]}

# printing result 
print("The Initialized dictionary : " + str(res)) 
```

**Output :**

```
The Initialized dictionary : {'gfg': [[], [], [], []], 'best': [[], [], [], []]}

```