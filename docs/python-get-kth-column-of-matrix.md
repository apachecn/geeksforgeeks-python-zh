# Python |获取矩阵第 Kth 列

> 原文:[https://www . geesforgeks . org/python-get-kth-column-of-matrix/](https://www.geeksforgeeks.org/python-get-kth-column-of-matrix/)

有时候，在使用 Python Matrix 时，可能会遇到一个问题，即需要找到 Matrix 的第 k 列。这是机器学习领域中一个非常普遍的问题，解决这个问题非常有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
这个问题可以通过使用列表理解来解决，在列表理解中，我们可以遍历所有行，并选择性地收集出现在第 Kth 索引处的所有元素。

```py
# Python3 code to demonstrate working of
# Get Kth Column of Matrix
# using list comprehension

# initialize list
test_list = [[4, 5, 6], [8, 1, 10], [7, 12, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initialize K
K = 2

# Get Kth Column of Matrix
# using list comprehension
res = [sub[K] for sub in test_list]

# printing result
print("The Kth column of matrix is : " + str(res))
```

**Output :**

```py
The original list is : [[4, 5, 6], [8, 1, 10], [7, 12, 5]]
The Kth column of matrix is : [6, 10, 5]

```