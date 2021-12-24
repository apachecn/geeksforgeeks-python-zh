# Python–获取矩阵平均值

> 原文:[https://www.geeksforgeeks.org/python-get-matrix-mean/](https://www.geeksforgeeks.org/python-get-matrix-mean/)

给定一个矩阵，找到它的平均值。

> **输入** : test_list = [[5，6，7]，[7，5，6]]
> **输出** : 6.0
> **解释** : 36 / 6 = 6.0
> 
> **输入** : test_list = [[5，6，7，4，8]]
> **输出** : 6.0
> **解释** : 30 / 5 = 6.0

**方法一:使用列表理解+ sum() + len() + zip()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 sum()和 len()，zip()和*运算符执行平均值计算，并提取矩阵行的每个元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Matrix Mean
# Using list comprehension + sum() + len() + zip()

# initializing lists
test_list = [[5, 6, 3], [8, 3, 1], [9, 10, 4], [8, 4, 2]]

# printing original list
print("The original list : " + str(test_list))

# zip() to get all elements 
# sum() / len() gives mean
# extracts column mean
res = [sum(idx) / len(idx) for idx in zip(*test_list)]

# extracts all elements mean
res = sum(res) / len(res)

# printing result 
print("Matrix Mean : " + str(res))
```

**Output**

```
The original list : [[5, 6, 3], [8, 3, 1], [9, 10, 4], [8, 4, 2]]
Matrix Mean : 5.25

```

**方法二:使用 mean() + zip() +列表理解**

这是可以执行此任务的另一种方法。在本文中，我们使用内置的均值()方法提取均值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Matrix Mean
# Using mean() + zip() + list comprehension
from statistics import mean

# initializing lists
test_list = [[5, 6, 3], [8, 3, 1], [9, 10, 4], [8, 4, 2]]

# printing original list
print("The original list : " + str(test_list))

# zip() to get all elements 
# mean() gives mean
# extracts column mean
res = [mean(idx) for idx in zip(*test_list)]

# extracts all elements mean
res = mean(res)

# printing result 
print("Matrix Mean : " + str(res))
```

**Output**

```
The original list : [[5, 6, 3], [8, 3, 1], [9, 10, 4], [8, 4, 2]]
Matrix Mean : 5.25

```