# Python 中的代数矩阵模块

> 原文:[https://www . geesforgeks . org/代数矩阵-python 中的模块/](https://www.geeksforgeeks.org/algebraonmatrix-module-in-python/)

**代数矩阵**模块是 python 库，帮助你执行基本矩阵代数，如两个矩阵的加法、两个矩阵的减法、两个矩阵的乘法、矩阵的转置。

### 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install AlgebraOnMatrix
```

### 代数矩阵的函数

**矩阵:**它会把我们的二维数组转换成矩阵。

**示例:**

```py
# Importing Matrix function  
# From AlgebraOnMatrix Library  
from AlgebraOnMatrix import Matrix

arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

# Now we will transform our 2d array
# into the matrix and make an object
# of it 
a = Matrix(arr)
```

### 矩阵运算

*   **Addition of Matrices :** Here we will add the matrix b with the matrix a where matrix b is given in 2d array .It will be done by function **Matrix.addition(a, b)** where a is a object which we have created and b is 2d array .
    **Example :**

    ```py
    # Importing Matrix function  
    # From AlgebraOnMatrix Library  
    from AlgebraOnMatrix import Matrix

    arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

    # Now we will transform our 2d array 
    # into matrix and make an object of it 
    a = Matrix(arr)

    b =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

    ans = Matrix.addition(a, b)
    print(ans)
    ```

    **输出:**

    ```py
    [[2, 4, 6], [8, 10, 12], [14, 16, 18]]

    ```

*   **Subtraction of Matrices :**Here we will subtract the matrix b from the matrix a where matrix b is given in 2d array .It will be done by function **Matrix.subtraction(a, b)** where a is a object which we have created and b is 2d array .
    **Example :**

    ```py
    # Importing Matrix function  
    # From AlgebraOnMatrix Library  
    from AlgebraOnMatrix import Matrix

    arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

    # Now we will transform our 2d array 
    # into matrix and make an object of it 
    a = Matrix(arr)

    b =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

    ans = Matrix.subtraction(a, b)
    print(ans)
    ```

    **输出:**

    ```py
    [[0, 0, 0], [0, 0, 0], [0, 0, 0]]

    ```

*   **Multiplication of Matrices :** Here we will multiply the matrix b with the matrix a where matrix b is given in 2d array .It will be done by function **Matrix.multiplication(a, b)** where a is a object which we have created and b is 2d array .
    **Example :**

    ```py
    # Importing Matrix function  
    # From AlgebraOnMatrix Library  
    from AlgebraOnMatrix import Matrix

    arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

    # Now we will transform our 2d array 
    # into matrix and make an object of it 
    a = Matrix(arr)

    b =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

    ans = Matrix.multiplication(a, b)
    print(ans)
    ```

    **输出:**

    ```py
    [[30, 36, 42], [66, 81, 96], [102, 126, 150]]

    ```

*   **Transpose of Matrix :**Here we will transpose the matrix a.It will be done by function **Matrix.transpose(a)** where a is a object which we have created
    **Example :**

    ```py
    # Importing Matrix function  
    # From AlgebraOnMatrix Library  
    from AlgebraOnMatrix import Matrix

    arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

    # Now we will transform our 2d array 
    # into matrix and make an object of it 

    a = Matrix(arr)

    ans = Matrix.transpose(a)
    print(ans)
    ```

    **输出:**

    ```py
    [[1, 4, 7], [2, 5, 8], [3, 6, 9]]

    ```