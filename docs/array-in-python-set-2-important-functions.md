# Python 中的数组|集合 2(重要功能)

> 原文:[https://www . geesforgeks . org/python 中的数组-set-2-重要-函数/](https://www.geeksforgeeks.org/array-in-python-set-2-important-functions/)

[Python 中的数组|集合 1(介绍和函数)](https://www.geeksforgeeks.org/array-python-set-1-introduction-functions/)

下面是一些更多的功能。

**1。类型代码** :-该函数**返回初始化数组的数据类型**。

**2。itemsize** :-该函数返回**大小**，单位为**单个数组元素的字节。**

**3。buffer_info()** :-返回一个元组，该元组表示存储数组的**地址和其中的元素数量**。

```
# Python code to demonstrate the working of 
# typecode, itemsize, buffer_info()

# importing "array" for array operations
import array

# initializing array with array values
# initializes array with signed integers
arr= array.array('i',[1, 2, 3, 1, 2, 5]) 

# using typecode to print datatype of array
print ("The datatype of array is : ")
print (arr.typecode)

# using itemsize to print itemsize of array
print ("The itemsize of array is : ")
print (arr.itemsize)

# using buffer_info() to print buffer info. of array
print ("The buffer info. of array is : ")
print (arr.buffer_info())
```

**输出:**

```
The datatype of array is : 
i
The itemsize of array is : 
4
The buffer info. of array is : 
(29784224, 6)

```

除了导入数组，我们还可以使用*来导入数组。

```
# importing "array" using * for array operations
from array import *

# initializing array with array values
# initializes array with signed integers
arr = array('i',[1, 2, 3, 1, 2, 5]) 

print(arr)
```

**输出:**

```
array('i', [1, 2, 3, 1, 2, 5])

```

**4。count()** :-这个函数**统计数组中提到的参数出现的次数**。

**5。extend(arr)** :-这个函数**将一个在其参数中提到的整个数组**追加到指定的数组中。

```
# Python code to demonstrate the working of 
# count() and extend()

# importing "array" for array operations
import array

# initializing array 1 with array values
# initializes array with signed integers
arr1 = array.array('i',[1, 2, 3, 1, 2, 5]) 

# initializing array 2 with array values
# initializes array with signed integers
arr2 = array.array('i',[1, 2, 3]) 

# using count() to count occurrences of 1 in array
print ("The occurrences of 1 in array is : ")
print (arr1.count(1))

# using extend() to add array 2 elements to array 1 
arr1.extend(arr2)

print ("The modified array is : ")
for i in range (0,9):
    print (arr1[i])
```

**输出:**

```
The occurrences of 1 in array is : 
2
The modified array is : 
1
2
3
1
2
5
1
2
3

```

**6。fromlist(list)** :-该函数用于**将参数**中提到的列表**追加到数组**的末尾。

**7。tolist()** :-该功能用于**将数组转换为列表**。

```
# Python code to demonstrate the working of 
# fromlist() and tolist()

# importing "array" for array operations
import array

# initializing array with array values
# initializes array with signed integers
arr = array.array('i',[1, 2, 3, 1, 2, 5]) 

# initializing list
li = [1, 2, 3]

# using fromlist() to append list at end of array
arr.fromlist(li)

# printing the modified array
print ("The modified array is : ",end="")
for i in range (0,9):
    print (arr[i],end=" ")

# using tolist() to convert array into list
li2 = arr.tolist()

print ("\r")

# printing the new list
print ("The new list created is : ",end="")
for i in range (0,len(li2)):
    print (li2[i],end=" ")
```

**输出:**

```
The modified array is : 1 2 3 1 2 5 1 2 3 
The new list created is : 1 2 3 1 2 5 1 2 3

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。