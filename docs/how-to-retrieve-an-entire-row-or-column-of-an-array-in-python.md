# 如何在 Python 中检索数组的整行或整列？

> 原文:[https://www . geeksforgeeks . org/如何检索 python 中的整行或整列数组/](https://www.geeksforgeeks.org/how-to-retrieve-an-entire-row-or-column-of-an-array-in-python/)

数组是一组组合在一起形成单个实体的类似元素，也就是说，它基本上是整数、浮点数、字符等的集合。行和列的索引从 0 开始。

### **一维阵列**

一维数组形成一个相似数据类型归属元素的向量。它包含一行元素，每一行都属于不同的列。一维数组的维数是[1×c]，其中 c 是列数。可以使用数组的相应索引来访问数组中的任何列。因为这个数组包含一行，所以打印数组相当于打印第一行。

```py
array - retrieves the column at cth index (c+1 row)

```

下面的 Python 代码演示了在一维数组中检索整个列的过程:

## 计算机编程语言

```py
# importing the required package
import numpy as np

# creating a numpy character array
arr1 = np.array(["Ram", "Shyam" , "Sita"])

print("First row - ")
print(arr1)

# printing first column referred by first index
print ("First Column")
print (arr1[0])

# computing length of array 
length = len(arr1)
print("Last Column")
print (arr1[length-1])
```

**输出:**

```py
Original Array -  
['Ram' 'Shyam' 'Sita']
First Column
Ram
Last Column
Sita

```

还可以通过指定开始和最后一个索引从一维数组中检索一系列列。如果我们不指定最后一个索引，数组会一直打印到数组的末尾。

> array[start:end]–从 start 索引到 end-1 索引检索数组列。

下面的 python 代码用于检索一维数组中的一系列列:

## 蟒蛇 3

```py
# importing the required package
import numpy as np

# creating a numpy integer array
arr1 = np.array([1, 2, 3, 4, 5, 6, 7, 8])

print("First two columns")
print(arr1[0:2])

# printing columns in a range
print("Columns in a range")
print(arr1[4:7])

# computing length of array
length = len(arr1)

print("Last 3 Columns")
print(arr1[length-3:length])

print("Array till the end")
print(arr1[3:])
```

**输出:**

```py
First two columns
[1 2]
Columns in a range
[5 6 7]
Last 3 Columns
[6 7 8]
Array till the end
[4 5 6 7 8]

```

### **多维数组**

多维数组是堆叠在一起形成矩阵的一系列行。矩阵包含类似的元素，属于整数、字符和双数。它由维数[r x c]表示，其中 r 是行数，c 是列数。

```py
matrix [r] - prints row at r index
matrix[ : , c] - prints column at c index

```

下面的 Python 代码演示了检索整行或一列的过程:

## 蟒蛇 3

```py
# importing the required package
import numpy as np

# creating a numpy integer array
mat1 = np.array([[1, 2, 3], [4, 5, 6]])

print("Original matrix ")
print(mat1)

print("Row at 0th index")
print(mat1[0])

# 1st columns
print("Column at 1st index")
print(mat1[:, 1])

# computing length of array
print("Column at 2nd index")
print(mat1[:, 2])
```

**输出:**

```py
Original matrix 
[[1 2 3]
 [4 5 6]]
Row at 0th index
[1 2 3]
Column at 1st index
[2 5]
Column at 2nd index
[3 6]

```

也可以打印属于矩阵中某个范围的行或列。我们指定矩阵的行和列的开始和结束索引。如果我们将结束索引留空，它将打印列或行，直到矩阵的长度。

## 蟒蛇 3

```py
# importing the required package
import numpy as np

# creating a numpy integer array
mat1 = np.array([[1, 2, 3, 4], [4, 5, 6, 8], [7, 6, 8, 9]])
print("Original matrix ")
print(mat1)

print("Row from 1st to 2nd index")
print(mat1[1:3])

# 1st columns
print("Last three columns")

# prints all the columns till the end
print(mat1[:, 1:])

# printing a subset of matrix
print("Matrix subset")
# row index 1 and 2 inclusive and col_index 2 and 3 inclusive
print(mat1[1:3, 2:4])
```

**输出:**

```py
Original matrix 
[[1 2 3 4]
 [4 5 6 8]
 [7 6 8 9]]
Row from 1st to 2nd index
[[4 5 6 8]
 [7 6 8 9]]
Last three columns
[[2 3 4]
 [5 6 8]
 [6 8 9]]
Matrix subset
[[6 8]
 [8 9]]

```