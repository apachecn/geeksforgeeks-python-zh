# Python–将元组矩阵转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-tuple-matrix-to-tuple-list/](https://www.geeksforgeeks.org/python-convert-tuple-matrix-to-tuple-list/)

给定一个元组矩阵，扁平化为元组列表，每个元组代表每一列。

> **输入**:test _ list =[(4，5)，(7，8)]，[(10，13)，(18，17)]
> **输出** : [(4，7，10，18)，(5，8，13，17)]
> **解释**:包含在一起的所有列号元素。
> 
> **输入**:test _ list =[(4，5)]，[(10，13)]
> **输出** : [(4，10)，(5，13)]
> **解释**:包含在一起的所有列号元素。

**方法#1:使用列表理解+ zip()**

在这种情况下，我们使用列表理解来执行展平任务，并使用 zip()来执行列配对以呈现为元组对。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Tuple Matrix to Tuple List
# Using list comprehension + zip()

# initializing list
test_list = [[(4, 5), (7, 8)], [(10, 13), (18, 17)], [(0, 4), (10, 1)]]

# printing original list
print("The original list is : " + str(test_list))

# flattening 
temp = [ele for sub in test_list for ele in sub]

# joining to form column pairs
res = list(zip(*temp))

# printing result 
print("The converted tuple list : " + str(res))
```

**Output**

```py
The original list is : [[(4, 5), (7, 8)], [(10, 13), (18, 17)], [(0, 4), (10, 1)]]
The converted tuple list : [(4, 7, 10, 18, 0, 10), (5, 8, 13, 17, 4, 1)]

```

**方法 2:使用 chain.from_iterable() + zip()**

在本例中，使用 chain.from_iterable()执行展平任务，使用 zip()执行列配对任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Tuple Matrix to Tuple List
# Using chain.from_iterable() + zip()
from itertools import chain

# initializing list
test_list = [[(4, 5), (7, 8)], [(10, 13), (18, 17)], [(0, 4), (10, 1)]]

# printing original list
print("The original list is : " + str(test_list))

# flattening using from_iterable
res = list(zip(*chain.from_iterable(test_list)))

# printing result 
print("The converted tuple list : " + str(res))
```

**Output**

```py
The original list is : [[(4, 5), (7, 8)], [(10, 13), (18, 17)], [(0, 4), (10, 1)]]
The converted tuple list : [(4, 7, 10, 18, 0, 10), (5, 8, 13, 17, 4, 1)]

```