# 在 Python 中初始化矩阵

> 原文:[https://www.geeksforgeeks.org/initialize-matrix-in-python/](https://www.geeksforgeeks.org/initialize-matrix-in-python/)

有时在竞争性编程的世界中，我们需要初始化矩阵，但是我们不希望使用循环以更长的方式来初始化矩阵。我们需要一个简写。这类问题在动态编程领域非常常见。让我们讨论一下实现这一点的某些方法。
**方法#1:使用列表理解**
列表理解可以被视为执行该特定操作的简写。在列表理解中，我们可以初始化内部列表，然后使用列表理解再次将这个逻辑扩展到每一行。

## 蟒蛇 3

```py
# Python3 code to demonstrate 
# initializing matrix
# using list comprehension

# Declaring rows
N = 5

# Declaring columns
M = 4

# using list comprehension 
# to initializing matrix
res = [ [ 0 for i in range(M) ] for j in range(N) ]

# printing result 
print("The matrix after initializing : " + str(res))
```

**Output**

```py
The matrix after initializing : [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]]

```

**方法 2:使用列表理解+“*”运算符**
这个问题也可以使用*运算符来简化，它可以稍微减少完成任务的繁琐方式，并且可以简单地使用乘法运算符将初始化扩展到所有 N 行。

## 蟒蛇 3

```py
# Python3 code to demonstrate 
# initializing matrix
# using list comprehension
# and * operator

# Declaring rows
N = 5

# Declaring columns
M = 4

# using list comprehension 
# to initializing matrix
res = [ [0 for i in range(M)]] * N

# printing result 
print("The matrix after initializing : " + str(res))
```

**Output**

```py
The matrix after initializing : [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]]

```

**方法#3:使用+“*”运算符两次**
与上面的示例类似，我们也可以使用“*”运算符初始化列两次。

## 蟒蛇 3

```py
# Python3 code to demonstrate 
# initializing matrix
# * operator twice

# By: Pushpak Jalan, Tezpur University

# Declaring rows
N = 5

# Declaring columns
M = 4

# Using * operator twice to initialize matrix
res = [[0] * M] * N

# printing result 
print("The matrix after initializing : " + str(res))
```

**Output**

```py
The matrix after initializing : [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]]

```