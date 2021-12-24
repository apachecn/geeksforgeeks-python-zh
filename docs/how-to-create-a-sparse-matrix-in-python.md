# 如何在 Python 中创建稀疏矩阵

> 原文:[https://www . geesforgeks . org/如何在 python 中创建稀疏矩阵/](https://www.geeksforgeeks.org/how-to-create-a-sparse-matrix-in-python/)

如果矩阵的大部分元素都有 **0 值** ，那么就称之为稀疏矩阵。使用稀疏矩阵代替 a 简单矩阵的两大好处是:

*   **存储:**非零元素比零少，因此可以使用更少的内存来仅存储这些元素。
*   **计算时间:**通过逻辑设计只遍历非零元素的数据结构，可以节省计算时间。

稀疏矩阵通常是在应用机器学习中使用的，例如在包含将类别映射到计数的数据编码的数据中，以及在机器学习的整个子领域中使用的，例如自然语言处理(NLP)。

**示例:**

```py
0 0 3 0 4            
0 0 5 7 0
0 0 0 0 0
0 2 6 0 0
```

用 2D 阵列表示稀疏矩阵会导致大量内存的浪费，因为矩阵中的零在大多数情况下都没有用。所以，我们不是用非零元素存储零，而是只存储非零元素。这意味着用 **三元组(行、列、值)存储非零元素。**

### 用 Python 创建稀疏矩阵

Python 的 **SciPy** 给出了使用多个数据结构创建稀疏矩阵的工具，以及将密集矩阵转换为稀疏矩阵的工具。函数**CSR _ matrix()**用于创建c压缩稀疏行格式的稀疏矩阵，而**CSC _ matrix()**用于创建c压缩稀疏列格式的稀疏矩阵。

#### **#使用****CSR _ matrix()**

> **语法:**
> 
> **scipy . sparse . CSR _ matrix****(***shape = None***、***dtype = None***)**
> 
> **参数:**
> 
> **形状:**获得矩阵形状
> 
> **数据类型:**矩阵的数据类型

**例 1:**

## 计算机编程语言

```py
# Python program to create
# sparse matrix using csr_matrix()

# Import required package
import numpy as np
from scipy.sparse import csr_matrix

# Creating a 3 * 4 sparse matrix
sparseMatrix = csr_matrix((3, 4), 
                          dtype = np.int8).toarray()

# Print the sparse matrix
print(sparseMatrix)
```

**输出:**

```py
[[0 0 0 0]
 [0 0 0 0]
 [0 0 0 0]]

```

**例 2:**

## 计算机编程语言

```py
# Python program to create
# sparse matrix using csr_matrix()

# Import required package
import numpy as np
from scipy.sparse import csr_matrix

row = np.array([0, 0, 1, 1, 2, 1])
col = np.array([0, 1, 2, 0, 2, 2])

# taking data
data = np.array([1, 4, 5, 8, 9, 6])

# creating sparse matrix
sparseMatrix = csr_matrix((data, (row, col)), 
                          shape = (3, 3)).toarray()

# print the sparse matrix
print(sparseMatrix)
```

**输出:**

```py
[[ 1  4  0]
 [ 8  0 11]
 [ 0  0  9]]

```

#### **#使用****CSC _ matrix()**

> **语法:**
> 
> **scipy . sparse . CSC _ matrix****(***shape = None***、***dtype = None***)**
> 
> **参数:**
> 
> **形状:**获得矩阵形状
> 
> **数据类型:**矩阵的数据类型

**例 1:**

## 计算机编程语言

```py
# Python program to create
# sparse matrix using csc_matrix()

# Import required package
import numpy as np
from scipy.sparse import csc_matrix

# Creating a 3 * 4 sparse matrix
sparseMatrix = csc_matrix((3, 4), 
                          dtype = np.int8).toarray()

# Print the sparse matrix
print(sparseMatrix)
```

**输出:**

```py
[[0 0 0 0]
 [0 0 0 0]
 [0 0 0 0]]

```

**例 2:**

## 计算机编程语言

```py
# Python program to create
# sparse matrix using csc_matrix()

# Import required package
import numpy as np
from scipy.sparse import csc_matrix

row = np.array([0, 0, 1, 1, 2, 1])
col = np.array([0, 1, 2, 0, 2, 2])

# taking data
data = np.array([1, 4, 5, 8, 9, 6])

# creating sparse matrix
sparseMatrix = csc_matrix((data, (row, col)),
                          shape = (3, 3)).toarray()

# print the sparse matrix
print(sparseMatrix)
```

**输出:**

```py
[[ 1  4  0]
 [ 8  0 11]
 [ 0  0  9]]

```