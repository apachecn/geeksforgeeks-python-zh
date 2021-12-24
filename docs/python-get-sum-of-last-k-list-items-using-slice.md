# Python–使用切片

获取最后 K 个列表项的总和

> 原文:[https://www . geesforgeks . org/python-get-sum-of-last-k-list-items-using-slice/](https://www.geeksforgeeks.org/python-get-sum-of-last-k-list-items-using-slice/)

访问列表中的元素有许多类型和变体。这些是 Python 编程必不可少的一部分，人们必须具备执行同样操作的知识。本文讨论了获取最后 K 个元素并进行求和的方法。让我们讨论执行此任务的特定解决方案。
**方法#1:使用列表切片+ sum()**
这个问题可以在一行中执行，而不是使用 Python 提供的列表切片功能使用循环，然后使用 sum()。减运算符指定从后端开始进行切片。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Inverse K slice Sum
# using list slicing + sum()

# initializing list
test_list = [4, 5, 2, 6, 7, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 5

# Inverse K slice Sum
# using list slicing + sum()
res = sum(test_list[-K:])

# print result
print("The last K elements sum of list is : " + str(res))
```

**Output : **

```
The original list : [4, 5, 2, 6, 7, 8, 10]
The last K elements sum of list is : 33
```

**方法 2:使用 islice()+reversed()+sum()**
内置的功能也可以用来执行这个特定的任务。islice 函数用于获取分片列表，reversed 函数用于获取后端元素，然后 sum()用于求和。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Inverse K slice Sum
# using islice() + reversed() + sum()
from itertools import islice

# initializing list
test_list = [4, 5, 2, 6, 7, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 5

# using islice() + reversed() + sum()
# Inverse K slice Sum
res = list(islice(reversed(test_list), 0, K))
res.reverse()
res = sum(res)

# print result
print("The last K elements sum of list are : " + str(res))
```

**Output : **

```
The original list : [4, 5, 2, 6, 7, 8, 10]
The last K elements sum of list is : 33
```