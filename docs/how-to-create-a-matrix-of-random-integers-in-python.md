# 如何在 Python 中创建随机整数矩阵？

> 原文:[https://www . geesforgeks . org/如何在 python 中创建随机整数矩阵/](https://www.geeksforgeeks.org/how-to-create-a-matrix-of-random-integers-in-python/)

**先决条件:**T2

为了在 Python 中创建随机整数矩阵，使用了 numpy 模块的 randint()函数。该函数用于随机抽样，即生成的所有数字都是随机的，无法直接预测。

> **语法:** numpy.random.randint(低，高=无，大小=无，数据类型='l ')
> 
> **参数:**
> 
> *   **低:**【int】从分布中抽取的最低(有符号)整数。但是，如果 high=None，它作为样本中的最高整数工作。
>     
> *   **高:**【int，可选】从分布中提取的最大(有符号)整数。
>     
> *   **大小:**【int 或 int 元组，可选】输出形状。如果给定的形状是例如(m，n，k)，则绘制 m * n * k 个样本。默认值为无，在这种情况下，将返回一个值。
>     
> *   **数据类型:**【可选】所需的输出数据类型。
> 
> **返回:**区间[低，高]内的随机整数数组，如果没有提供大小，则返回一个这样的随机整数。

**例 1:**

## 蟒蛇 3

```
# importing numpy library
import numpy as np  

# random is a function, doing random sampling in numpy.
array = np.random.randint(10, size=(20))

# the array will be having 20 elements.
print(array)
```

**输出:**

> [2 6 1 4 3 3 6 5 0 3 6 8 9 1 6 4 0 5 4 1]

**例 2:**

## 蟒蛇 3

```
import numpy as np

# 1st argument --> numbers ranging from 0 to 9, 
# 2nd argument, row = 2, col = 3
array = np.random.randint(10, size=(2, 3))
print(array)
```