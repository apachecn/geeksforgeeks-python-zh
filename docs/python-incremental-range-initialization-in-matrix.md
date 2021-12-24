# Python–矩阵中的增量范围初始化

> 原文:[https://www . geesforgeks . org/python-增量-范围-矩阵中的初始化/](https://www.geeksforgeeks.org/python-incremental-range-initialization-in-matrix/)

有时候，在使用 Python 时，我们可能会遇到一个问题，需要执行 Matrix 的初始化。初始化越简单越容易。但有时，我们需要执行范围增量初始化。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们遍历列表，用指定的范围增加元素的值。

```py
# Python3 code to demonstrate 
# Incremental Range Initialization in Matrix
# using loop

# Initializing row
r = 4

# Initializing col
c = 3

# Initializing range 
rang = 5

# Incremental Range Initialization in Matrix
# using loop
res = []
temp = []
temp2 = 0
for idx in range(r):
    for idx in range(c):
        temp.append(temp2)
        temp2 = temp2 + rang
    res.append(temp)
    temp = []

# printing result 
print ("Matrix after Initialization : " + str(res))
```

**Output :**

```py
Matrix after Initialization : [[0, 5, 10], [15, 20, 25], [30, 35, 40], [45, 50, 55]]

```