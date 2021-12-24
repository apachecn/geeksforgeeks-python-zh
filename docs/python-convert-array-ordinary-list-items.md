# Python |把一个数组转换成一个普通的列表，里面有相同的项目

> 原文:[https://www . geesforgeks . org/python-convert-array-普通-list-items/](https://www.geeksforgeeks.org/python-convert-array-ordinary-list-items/)

前提条件:[Python 中的数组](https://www.geeksforgeeks.org/array-python-set-1-introduction-functions/)

Python 程序，用于将一个数组转换为具有相同项目的普通列表。

**示例:**

```
Input : array('i', [1, 3, 5, 3, 7, 1, 9, 3])
Output :[1, 3, 5, 3, 7, 1, 9, 3]
Explanation: the array with elements [1, 3, 5, 3, 
7, 1, 9, 3] are converted into list with the 
same elements.

Input :array('k', [45, 23, 56, 12])
Output :[45, 23, 56, 12]
Explanation: the array with elements [45, 23, 56, 
12] are converted into list with the same elements.

```

**处理问题的方法:**
我们想把一个数组转换成一个普通的列表，里面有相同的项目。为此，我们需要使用一个函数

```
// This function tolist() converts the array into a list.
arrayname.tolist()
```

```
from array import *
def array_list(array_num):
    num_list = array_num.tolist() # list
    print(num_list)

# driver code
array_num = array('i', [45,34,67]) # array
array_list(array_num)
```

输出:

```
[45, 34, 67]

```