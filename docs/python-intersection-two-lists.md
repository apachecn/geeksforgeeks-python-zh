# Python |两个列表的交集

> 原文:[https://www . geesforgeks . org/python-交集-两个列表/](https://www.geeksforgeeks.org/python-intersection-two-lists/)

两个列表的交集意味着我们需要获取两个初始列表共有的所有元素，并将它们存储到另一个列表中。现在在 Python 中有各种各样的方法，通过它们我们可以执行列表的交集。
示例:

```
Input : 
lst1 = [15, 9, 10, 56, 23, 78, 5, 4, 9]
lst2 = [9, 4, 5, 36, 47, 26, 10, 45, 87]
Output :
[9, 10, 4, 5]

Input :
lst1 = [4, 9, 1, 17, 11, 26, 28, 54, 69]
lst2 = [9, 9, 74, 21, 45, 11, 63, 28, 26]
Output :
[9, 11, 26, 28]
```

**方法 1:**
这是我们没有使用任何内置函数的最简单的方法。

## 蟒蛇 3

```
# Python program to illustrate the intersection
# of two lists in most simple way
def intersection(lst1, lst2):
    lst3 = [value for value in lst1 if value in lst2]
    return lst3

# Driver Code
lst1 = [4, 9, 1, 17, 11, 26, 28, 54, 69]
lst2 = [9, 9, 74, 21, 45, 11, 63, 28, 26]
print(intersection(lst1, lst2))
```

输出:

```
[9, 11, 26, 28]
```

**法二:**
此法包括使用**套()法**。

## 蟒蛇 3

```
# Python program to illustrate the intersection
# of two lists using set() method
def intersection(lst1, lst2):
    return list(set(lst1) & set(lst2))

# Driver Code
lst1 = [15, 9, 10, 56, 23, 78, 5, 4, 9]
lst2 = [9, 4, 5, 36, 47, 26, 10, 45, 87]
print(intersection(lst1, lst2))
```

输出:

```
[9, 10, 4, 5]
```

**方法三:**
在这个方法中我们**设置()较大的列表**，然后使用内置的函数**交集()**计算相交列表。**交集()**是集合的一级部分。

## 蟒蛇 3

```
# Python program to illustrate the intersection
# of two lists using set() and intersection()
def Intersection(lst1, lst2):
    return set(lst1).intersection(lst2)

# Driver Code
lst1 = [ 4, 9, 1, 17, 11, 26, 28, 28, 26, 66, 91]
lst2 = [9, 9, 74, 21, 45, 11, 63]
print(Intersection(lst1, lst2))
```

输出:

```
{9, 11}
```

**方法 4:**
通过使用这个**混合方法**程序的复杂度下降到 O(n)。这是执行以下程序的有效方法。

## 蟒蛇 3

```
# Python program to illustrate the intersection
# of two lists
def intersection(lst1, lst2):

    # Use of hybrid method
    temp = set(lst2)
    lst3 = [value for value in lst1 if value in temp]
    return lst3

# Driver Code
lst1 = [9, 9, 74, 21, 45, 11, 63]
lst2 = [4, 9, 1, 17, 11, 26, 28, 28, 26, 66, 91]
print(intersection(lst1, lst2))
```

输出:

```
[9, 9, 11]
```

**方法 5:**
这是在其他列表内部的子列表上执行交集的地方。这里我们使用了**滤镜的概念()。**

## 蟒蛇 3

```
# Python program to illustrate the intersection
# of two lists, sublists and use of filter()
def intersection(lst1, lst2):
    lst3 = [list(filter(lambda x: x in lst1, sublist)) for sublist in lst2]
    return lst3

# Driver Code
lst1 = [1, 6, 7, 10, 13, 28, 32, 41, 58, 63]
lst2 = [[13, 17, 18, 21, 32], [7, 11, 13, 14, 28], [1, 5, 6, 8, 15, 16]]
print(intersection(lst1, lst2))
```

**工作:**过滤器部分获取每个子列表的项目，并检查它是否在源列表中。对列表 2 中的每个子列表执行列表理解。
产量:

```
[[13, 32], [7, 13, 28], [1, 6]]
```