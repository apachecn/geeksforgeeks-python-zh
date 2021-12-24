# 用 Python 计算矩阵的标准差

> 原文:[https://www . geesforgeks . org/compute-python 中矩阵的标准偏差/](https://www.geeksforgeeks.org/calculate-standard-deviation-of-a-matrix-in-python/)

在本文中，我们将学习如何使用 Python 计算矩阵的标准差。

标准差用于衡量数据集中值的分布。它表示数据集中值的变化或分散，还有助于确定模型统计结论的可信度。它由σ表示，通过取方差的平方根来计算。如果标准差较低，则意味着大多数值更接近平均值，如果标准差较高，则意味着更接近平均值。在本文中，我们将学习 Python 中计算 SD 的不同方法。

我们可以使用以下方法计算标准偏差:

1.  NumPy 包中的 std()方法
2.  统计包中的 stdev()方法

**方法 1:**NumPy 包中的 std()方法。

## 蟒蛇 3

```py
# import required packages
import numpy as np

# Create matrix
matrix = np.array([[33, 55, 66, 74], [23, 45, 65, 27],
                  [87, 96, 34, 54]])

print("Your matrix:\n", matrix)

# use std() method
sd = np.std(matrix)
print("Standard Deviation :\n", sd)
```

**输出:**

```py
Your matrix:
[[33 55 66 74]
[23 45 65 27]
[87 96 34 54]]
Standard Deviation :
22.584870796373593

```

**方法 2:**Statistics 包中的 stdev()方法。

## 蟒蛇 3

```py
import statistics

statistics.stdev([11, 43, 56, 77, 87, 45, 67, 33])
```

**输出:**

```py
24.67466890789592

```