# Python 中的数组复制

> 原文:[https://www.geeksforgeeks.org/array-copying-in-python/](https://www.geeksforgeeks.org/array-copying-in-python/)

让我们看看如何在 Python 中复制数组。复制数组有 3 种方法:

*   Just use the assignment operator.

*   Deep imitation

### 分配数组

我们可以使用赋值运算符(=)来创建数组的副本。

**语法:**

```py
new_arr = old_ arr
```

在 Python 中，赋值语句不复制对象，而是在目标和对象之间创建绑定。当我们使用=运算符时，用户认为这创建了一个新对象；嗯，没有。它只创建一个共享原始对象引用的新变量。

**例:**

## 蟒 3

```py
# importing the module
from numpy import *                  

# creating the first array
arr1 = array([2, 6, 9, 4])            

# displaying the identity of arr1
print(id(arr1))

# assigning arr1 to arr2
arr2 = arr1                         

# displaying the identity of arr2
print(id(arr2))

# making a change in arr1
arr1[1] = 7                        

# displaying the arrays
print(arr1)
print(arr2)
```

**输出:**

```py
117854800
117854800
[2 7 9 4]
[2 7 9 4]
```

我们可以看到两个数组引用了同一个对象。

### 浅拷贝

浅拷贝意味着构建一个新的集合对象，然后用对在原始集合中找到的子对象的引用填充它。复制过程不会重复，因此不会创建子对象本身的副本。在浅复制的情况下，对象的引用被复制到另一个对象中。这意味着对对象副本所做的任何更改都会反映在原始对象中。我们将使用**视图()**功能实现浅层复制。

**例:**

## 蟒 3

```py
# importing the module
from numpy import *                 

# creating the first array
arr1 = array([2, 6, 9, 4])

# displaying the identity of arr1
print(id(arr1))

# shallow copy arr1 in arr2 using view()
arr2 = arr1.view() 

# displaying the identity of arr2
print(id(arr2))

# making a change in arr1
arr1[1] = 7                       

# displaying the arrays
print(arr1)
print(arr2)
```

这一次，虽然两个数组引用了不同的对象，但是在改变一个数组的值时，另一个数组的值也会改变。

### 深度复制

深度复制是复制过程递归发生的过程。这意味着首先构造一个新的集合对象，然后递归地用在原始集合中找到的子对象的副本填充它。在深度复制的情况下，对象的副本被复制到另一个对象中。这意味着对对象副本所做的任何更改都不会反映在原始对象中。我们将使用 **copy()** 功能实现深度复制。

## 蟒 3

```py
# importing the module
from numpy import *                 

# creating the first array
arr1 = array([2, 6, 9, 4])

# displaying the identity of arr1
print(id(arr1))

# shallow copy arr1 in arr2 using view()
arr2 = arr1.copy()

# displaying the identity of arr2
print(id(arr2))

# making a change in arr1
arr1[1] = 7                       

# displaying the arrays
print(arr1)
print(arr2)
```

**输出:**

```py
121258976
125714048
[2 7 9 4]
[2 6 9 4]
```

这一次，一个数组中的更改不会反映在另一个数组中。

## 深度复制继续

如果你处理的是 NumPy 矩阵，那么 numpy.copy()会给你一个深度副本。然而，如果你的矩阵仅仅是一个列表，那么在将一个图像(表示为一个列表的列表)旋转 90 度的任务中，考虑以下两种方法:

## 

```py
import copy

def rotate_matrix(image):
    # Copy method one
    copy_image_one = copy.deepcopy(image)
    print("Original", matrix)
    print("Copy of original", copy_image_one)
    N = len(matrix)

    # Part 1, reverse order within each row
    for row in range(N):
        for column in range(N):
            copy_image_one[row][column] = image[row][N-column-1]

    print("After modification")
    print("Original", matrix)
    print("Copy", copy_image_one)

    # Copy method two
    copy_image_two = [list(row) for row in copy_image_one]
    # Test on what happens when you remove list from the above code.

    # Part 2, transpose
    for row in range(N):
        for column in range(N):
            copy_image_two[column][row] = copy_image_one[row][column]

    return copy_image_two

if __name__ == "__main__":
    matrix = [[1, 2, 3],
              [4, 5, 6],
              [7, 8, 9]]
    print("Rotated image", rotate_matrix(matrix))
```

**输出:**

```py
Original [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
Copy of original [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
After modification
Original [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
Copy [[3, 2, 1], [6, 5, 4], [9, 8, 7]]
Rotated image [[3, 6, 9], [2, 5, 8], [1, 4, 7]]
```