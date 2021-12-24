# Python–增量 K 大小行矩阵初始化

> 原文:[https://www . geeksforgeeks . org/python-增量-k 大小-行-矩阵-初始化/](https://www.geeksforgeeks.org/python-incremental-k-sized-row-matrix-initialization/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要使用增量数对矩阵进行初始化。这种应用可以出现在数据科学领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+列表切片**
这个任务可以使用循环以暴力的方式执行。在这种情况下，我们运行一个跳过 K(所需行大小)的循环，以提前调整数字加法。

```
# Python3 code to demonstrate 
# Incremental K sized Row Matrix Initialization
# using loop + list slicing

# Initialization of row size 
K = 3

# Incremental K sized Row Matrix Initialization
# using loop + list slicing
res = []
for idx in range(1, 10, K):
    sub = [idx, idx + 1, idx + 2]
    res.append(sub)

# printing result 
print ("The Incremental Initialized Matrix is : " + str(res))
```

**Output :**

```
The Incremental Initialized Matrix is : [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

```