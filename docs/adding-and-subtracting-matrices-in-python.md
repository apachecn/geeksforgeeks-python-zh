# Python 中的加减矩阵

> 原文:[https://www . geesforgeks . org/python 中的加减矩阵/](https://www.geeksforgeeks.org/adding-and-subtracting-matrices-in-python/)

在本文中，我们将讨论如何在 Python 中加减矩阵元素。

**示例:**

```py
Suppose we have two matrices A and B.
A = [[1,2],[3,4]]
B = [[4,5],[6,7]]

then we get
A+B = [[5,7],[9,11]]
A-B = [[-3,-3],[-3,-3]]

```

现在让我们尝试使用 Python 来实现这一点

**1。添加矩阵元素**

在上面的代码中，我们使用了 [np.add()](https://www.geeksforgeeks.org/numpy-add-in-python/#:~:text=add()%20function%20is%20used,not%20same%2C%20that%20is%20arr1.) 方法来添加两个矩阵的元素。如果两个数组的形状不一样，那就是 arr1.shape！= arr2.shape 它们必须是可广泛铸造的共同形状(可以是一个或另一个的形状)。

## 蟒蛇 3

```py
# importing numpy as np
import numpy as np

# creating first matrix
A = np.array([[1, 2], [3, 4]])

# creating second matrix
B = np.array([[4, 5], [6, 7]])

print("Printing elements of first matrix")
print(A)
print("Printing elements of second matrix")
print(B)

# adding two matrix
print("Addition of two matrix")
print(np.add(A, B))
```

**输出:**

```py
Printing elements of first matrix
[[1 2]
 [3 4]]
Printing elements of second matrix
[[4 5]
 [6 7]]
Addition of two matrix
[[ 5  7]
 [ 9 11]]
```

**2。减去矩阵的元素**

在上面的代码中，我们使用了 [np .减法()](https://www.geeksforgeeks.org/numpy-subtract-in-python/#:~:text=subtract()%20function%20is%20used,and%20arr2%2C%20element%2Dwise.)来减去两个矩阵的元素。它按元素返回 arr1 和 arr2 的差值。

## 蟒蛇 3

```py
# importing numpy as np
import numpy as np

# creating first matrix
A = np.array([[1, 2], [3, 4]])

# creating second matrix
B = np.array([[4, 5], [6, 7]])

print("Printing elements of first matrix")
print(A)
print("Printing elements of second matrix")
print(B)

# subtracting two matrix
print("Subtraction of two matrix")
print(np.subtract(A, B))
```

**输出:**

```py
Printing elements of first matrix
[[1 2]
 [3 4]]
Printing elements of second matrix
[[4 5]
 [6 7]]
Subtraction of two matrix
[[-3 -3]
 [-3 -3]]
```