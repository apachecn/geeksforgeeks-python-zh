# Python |嵌套列表的列式求和

> 原文:[https://www . geesforgeks . org/python-column-wise-sum-nested-list/](https://www.geeksforgeeks.org/python-column-wise-sum-of-nested-list/)

给定一个嵌套列表(其中子列表的长度相等)，编写一个 Python 程序来查找给定列表的列总和，并将其返回到一个新列表中。

**示例:**

```
Input : [[1, 5, 3],
         [2, 7, 8],
         [4, 6, 9]]
Output : [7, 18, 20]

Input : [[20, 5],
         [2, 54],
         [45, 9], 
         [72, 3]]
Output : [139, 71]

```

**方法#1 :** *压缩*使用列表理解

我们可以使用 python 的`zip` 函数找到给定嵌套列表的每一列的总和，并将其包含在列表理解中。

```
# Python3 program to Column wise sum of nested list

def column_sum(lst):

     return [sum(i) for i in zip(*lst)]

# Driver code
lst = [[1, 5, 3], [2, 7, 8], [4, 6, 9]]
print(column_sum(lst))
```

**Output:**

```
[7, 18, 20]

```

**方法 2 :** 使用*地图()*方法

另一种方法是使用 *map()* 。我们将*求和*函数应用于一列中的每个元素，并相应地求出每列的和。

```
# Python3 program to Column wise sum of nested list

def column_sum(lst):

    return list(map(sum, zip(*lst)))

# Driver code
lst = [[1, 5, 3], [2, 7, 8], [4, 6, 9]]
print(column_sum(lst))
```

**Output:**

```
[7, 18, 20]

```

**方法#3 :** 使用 *numpy.sum()*

*numpy.sum()* 函数返回指定轴上数组元素的总和。

```
# Python3 program to Column wise sum of nested list
from numpy import array

def column_sum(lst):
    arr = array(lst)
    return sum(arr, 0).tolist()

# Driver code
lst = [[1, 5, 3], [2, 7, 8], [4, 6, 9]]
print(column_sum(lst))
```

**Output:**

```
[7, 18, 20]

```