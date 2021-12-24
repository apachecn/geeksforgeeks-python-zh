# Python–K 矩阵初始化

> 原文:[https://www . geesforgeks . org/python-k-matrix-初始化/](https://www.geeksforgeeks.org/python-k-matrix-initialization/)

有时在竞争性编程的世界中，我们需要初始化矩阵，但是我们不希望使用循环以更长的方式来完成。我们需要一个简写。这类问题在动态编程领域非常常见。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
列表理解可以被视为执行该特定操作的简写。在列表理解中，我们可以用 K 初始化内部列表，然后使用列表理解将这个逻辑再次扩展到每一行。

```py
# Python3 code to demonstrate 
# K Matrix Initialization 
# using list comprehension

# Declaring rows
N = 5

# Declaring columns
M = 4

# initializing K 
K = 7

# using list comprehension 
# to initializing matrix
res = [ [ K for i in range(N) ] for j in range(M) ]

# printing result 
print("The matrix after initializing with K : " + str(res))
```

**Output :**

```py
The matrix after initializing with K : [[7, 7, 7, 7, 7], [7, 7, 7, 7, 7], [7, 7, 7, 7, 7], [7, 7, 7, 7, 7]]

```