# 在 Python 中遍历列表

> 原文:[https://www . geesforgeks . org/iterate-over-a-list-in-python/](https://www.geeksforgeeks.org/iterate-over-a-list-in-python/)

[List](https://www.geeksforgeeks.org/python-list/) 相当于其他语言的数组，额外的好处是大小是动态的。在 Python 中，列表是数据结构中的一种容器，用于同时存储多个数据。与集合不同，Python 中的列表是有序的，并且有明确的计数。

在 Python 中，有多种方法可以遍历列表。让我们看看 Python 中迭代列表的所有不同方法，以及它们之间的性能比较。

**方法#1:** 使用 For 循环

## 蟒蛇 3

```
# Python3 code to iterate over a list
list = [1, 3, 5, 7, 9]

# Using for loop
for i in list:
    print(i)
```

**输出:**

```
1
3
5
7
9
```

**方法#2:** For 循环和 range()
如果我们想使用从数字 x 迭代到数字 y 的传统 For 循环

## 蟒蛇 3

```
# Python3 code to iterate over a list
list = [1, 3, 5, 7, 9]

# getting length of list
length = len(list)

# Iterating the index
# same as 'for i in range(len(list))'
for i in range(length):
    print(list[i])
```

**输出:**

```
1
3
5
7
9
```

如果我们可以迭代元素(如方法#1 中所做的)，不建议使用索引进行迭代。

**方法#3:** 使用 while 循环

## 蟒蛇 3

```
# Python3 code to iterate over a list
list = [1, 3, 5, 7, 9]

# Getting length of list
length = len(list)
i = 0

# Iterating using while loop
while i < length:
    print(list[i])
    i += 1
```

**输出:**

```
1
3
5
7
9
```

**方法#4:** 使用列表理解(可能是最具体的方式)。

## 蟒蛇 3

```
# Python3 code to iterate over a list
list = [1, 3, 5, 7, 9]

# Using list comprehension
[print(i) for i in list]
```

**输出:**

```
1
3
5
7
9
```

**方法#5:** 使用 enumerate()
如果我们想要将列表转换为元组的可迭代列表(或者基于条件检查获得索引，例如在线性搜索中，您可能需要保存最小元素的索引)，您可以使用 enumerate()函数。

## 蟒蛇 3

```
# Python3 code to iterate over a list
list = [1, 3, 5, 7, 9]

# Using enumerate()
for i, val in enumerate(list):
    print (i, ",",val)
```

**输出:**

```
0 , 1
1 , 3
2 , 5
3 , 7
4 , 9
```

**注意:**即使*方法#2* 也可以用来查找索引，但是*方法#1* 不能(除非每次迭代都增加一个额外的变量)*方法#5* 给出了该索引的简洁表示。

**方法#6:** 使用 numpy
对于非常大的 n 维列表(例如图像数组)，有时最好使用 numpy 之类的外部库。

## 蟒蛇 3

```
# Python program for
# iterating over array
import numpy as geek

# creating an array using 
# arrange method
a = geek.arange(9)

# shape array with 3 rows 
# and 4 columns
a = a.reshape(3, 3)

# iterating an array
for x in geek.nditer(a):
    print(x)
```

**输出:**

```
0
1
2
3
4
5
6
7
8
```

我们可以使用 np.ndenumerate()来模拟枚举的行为。NumPy 的额外能力来自于这样一个事实:我们甚至可以控制访问元素的方式(比如说 Fortran 顺序而不是 C 顺序:)，但是有一点需要注意，np.nditer 默认情况下将数组视为只读的，因此必须传递额外的标志，比如 op_flags=['readwrite']才能修改元素。