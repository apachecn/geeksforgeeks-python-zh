# Python |从给定列表中获取最后 N 个元素

> 原文:[https://www . geesforgeks . org/python-get-last-n-elements-from-given-list/](https://www.geeksforgeeks.org/python-get-last-n-elements-from-given-list/)

访问列表中的元素有许多类型和变体。这些是 Python 编程必不可少的一部分，人们必须具备执行同样操作的知识。本文讨论了获取列表最后 N 个元素的方法。让我们讨论执行此任务的特定解决方案。
**方法#1:使用列表切片**
这个问题可以在一行中执行，而不是使用 Python 提供的列表切片功能使用循环。减运算符指定从后端开始进行切片。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Get last N elements from list
# using list slicing

# initializing list
test_list = [4, 5, 2, 6, 7, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# initializing N
N = 5

# using list slicing
# Get last N elements from list
res = test_list[-N:]

# print result
print("The last N elements of list are : " + str(res))
```

**Output : **

```py
The original list : [4, 5, 2, 6, 7, 8, 10]
The last N elements of list are : [2, 6, 7, 8, 10]
```

**方法 2:使用 islice() + reversed()**
内置的功能也可以用来执行这个特定的任务。islice 函数可用于获取切片列表，reversed 函数用于从后端获取元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Get last N elements from list
# using islice() + reversed()
from itertools import islice

# initializing list
test_list = [4, 5, 2, 6, 7, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# initializing N
N = 5

# using islice() + reversed()
# Get last N elements from list
res = list(islice(reversed(test_list), 0, N))
res.reverse()

# print result
print("The last N elements of list are : " + str(res))
```

**Output : **

```py
The original list : [4, 5, 2, 6, 7, 8, 10]
The last N elements of list are : [2, 6, 7, 8, 10]
```