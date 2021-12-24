# Python |多个列表的交集

> 原文:[https://www . geesforgeks . org/python-多列表交集/](https://www.geeksforgeeks.org/python-intersection-of-multiple-lists/)

给定两个列表，编写一个 Python 程序来查找给定的两个列表之间的交集。

**示例:**

```
Input : lst1 = [['a', 'c'], ['d', 'e']]
        lst2 = [['a', 'c'], ['e', 'f'], ['d', 'e']]
Output : [['a', 'c'], ['d', 'e']]

Input : lst1 = [[1, 5, 7], [2, 3], [6, 9], [4, 8]]
        lst2 = [[9, 3], [2, 3], [6, 9]]
Output : [[2, 3], [6, 9]]

```

**接近#1 :** 幼稚(列表理解)

寻找列表交集的强力或天真方法是使用列表理解或简单的循环的*。*

```
# Python3 program to find 
# Intersection of list of lists

def intersection(lst1, lst2):

    return [item for item in lst1 if item in lst2]

# Driver code
lst1 = [['a', 'c'], ['d', 'e']]
lst2 = [['a', 'c'], ['e', 'f'], ['d', 'e']]
print(intersection(lst1, lst2))
```

**Output:**

```
[['a', 'c'], ['d', 'e']]

```

**进场#2 :** 使用集合*路口()*

与天真的方法相比，这是一种有效的方法。我们首先使用 *map()* 将这两个列表列表转换为元组列表，因为 Python 集与元组兼容，而不是列表。然后我们简单地找到这两个列表的集合*交集()*。

```
# Python3 program to find 
# Intersection of list of list

def intersection(lst1, lst2):
    tup1 = map(tuple, lst1)
    tup2 = map(tuple, lst2) 
    return list(map(list, set(tup1).intersection(tup2)))

# Driver code
lst1 = [['a', 'c'], ['d', 'e']]
lst2 = [['a', 'c'], ['e', 'f'], ['d', 'e']]
print(intersection(lst1, lst2))
```

**Output:**

```
[['d', 'e'], ['a', 'c']]

```