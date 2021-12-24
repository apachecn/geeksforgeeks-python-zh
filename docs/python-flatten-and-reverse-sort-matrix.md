# Python |展平和反向排序矩阵

> 原文:[https://www . geesforgeks . org/python-扁平化-反向-排序-矩阵/](https://www.geeksforgeeks.org/python-flatten-and-reverse-sort-matrix/)

列表的列表扁平化已经讨论过很多次了，但是有时候除了扁平化之外，还需要以反向排序的方式获取字符串。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`sorted() + reverse` +列表理解**
这个想法类似于展平一个列表的列表，但是除此之外，我们还添加了一个排序函数和 reverse 作为关键字，对列表理解返回的展平列表进行反向排序。

```py
# Python3 code to demonstrate
# Flatten and Reverse Sort Matrix
# using sorted + list comprehension

# initializing list of list 
test_list = [[3, 5], [7, 3, 9], [1, 12]]

# printing original list of list 
print("The original list : " + str(test_list))

# using sorted + list comprehension
# Flatten and Reverse Sort Matrix
res = sorted([j for i in test_list for j in i], reverse = True)

# print result
print("The reverse sorted and flattened list : " + str(res))
```

**Output :**

```py
The original list : [[3, 5], [7, 3, 9], [1, 12]]
The reverse sorted and flattened list : [12, 9, 7, 5, 3, 3, 1]

```