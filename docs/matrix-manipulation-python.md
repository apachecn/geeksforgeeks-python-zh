# Python 中的矩阵操作

> 原文:[https://www.geeksforgeeks.org/matrix-manipulation-python/](https://www.geeksforgeeks.org/matrix-manipulation-python/)

在 python 中矩阵可以实现为 2D [列表](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/)或者 2D 数组。从后者形成矩阵，提供了在矩阵中执行各种操作的附加功能。这些操作和[数组](https://www.geeksforgeeks.org/array-python-set-1-introduction-functions/)在模块 **numpy** 中定义。

**矩阵运算:**

**1。add() :-** 该功能用于执行**元素矩阵加法**。

**2。减法():-** 该功能用于执行**元素矩阵减法**。

**3。divide() :-** 此功能用于执行**元素矩阵划分**。

```
# Python code to demonstrate matrix operations
# add(), subtract() and divide()

# importing numpy for matrix operations
import numpy

# initializing matrices
x = numpy.array([[1, 2], [4, 5]])
y = numpy.array([[7, 8], [9, 10]])

# using add() to add matrices
print ("The element wise addition of matrix is : ")
print (numpy.add(x,y))

# using subtract() to subtract matrices
print ("The element wise subtraction of matrix is : ")
print (numpy.subtract(x,y))

# using divide() to divide matrices
print ("The element wise division of matrix is : ")
print (numpy.divide(x,y))
```

输出:

```
The element wise addition of matrix is : 
[[ 8 10]
 [13 15]]
The element wise subtraction of matrix is : 
[[-6 -6]
 [-5 -5]]
The element wise division of matrix is : 
[[ 0.14285714  0.25      ]
 [ 0.44444444  0.5       ]]

```

**4。乘法():-** 该函数用于执行**元素矩阵乘法**。

**5。dot() :-** 该函数用于计算**矩阵乘法，而不是元素乘法**。

```
# Python code to demonstrate matrix operations
# multiply() and dot()

# importing numpy for matrix operations
import numpy

# initializing matrices
x = numpy.array([[1, 2], [4, 5]])
y = numpy.array([[7, 8], [9, 10]])

# using multiply() to multiply matrices element wise
print ("The element wise multiplication of matrix is : ")
print (numpy.multiply(x,y))

# using dot() to multiply matrices
print ("The product of matrices is : ")
print (numpy.dot(x,y))
```

输出:

```
The element wise multiplication of matrix is : 
[[ 7 16]
 [36 50]]
The product of matrices is : 
[[25 28]
 [73 82]]

```

**6。sqrt() :-** 此函数用于计算矩阵各元素的**平方根。**

**7。sum(x，轴):-** 此功能用于**添加矩阵**中的所有元素。可选的“轴”参数在轴为 0 时计算**列和，在轴为 1 时计算**行和。****

**8。“T”:-**此参数用于**转置**指定的矩阵。

```
# Python code to demonstrate matrix operations
# sqrt(), sum() and "T"

# importing numpy for matrix operations
import numpy

# initializing matrices
x = numpy.array([[1, 2], [4, 5]])
y = numpy.array([[7, 8], [9, 10]])

# using sqrt() to print the square root of matrix
print ("The element wise square root is : ")
print (numpy.sqrt(x))

# using sum() to print summation of all elements of matrix
print ("The summation of all matrix element is : ")
print (numpy.sum(y))

# using sum(axis=0) to print summation of all columns of matrix
print ("The column wise summation of all matrix  is : ")
print (numpy.sum(y,axis=0))

# using sum(axis=1) to print summation of all columns of matrix
print ("The row wise summation of all matrix  is : ")
print (numpy.sum(y,axis=1))

# using "T" to transpose the matrix
print ("The transpose of given matrix is : ")
print (x.T)
```

输出:

```
The element wise square root is : 
[[ 1\.          1.41421356]
 [ 2\.          2.23606798]]
The summation of all matrix element is : 
34
The column wise summation of all matrix  is : 
[16 18]
The row wise summation of all matrix  is : 
[15 19]
The transpose of given matrix is : 
[[1 4]
 [2 5]]

```

本文由 **[曼吉特·辛格 100 投稿🙂](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。