# 用 Python 计算字典的标准差

> 原文:[https://www . geesforgeks . org/compute-python 字典标准差/](https://www.geeksforgeeks.org/calculate-standard-deviation-of-a-dictionary-in-python/)

Python 字典是一种通用的数据结构，可以轻松完成大量操作。计算标准偏差如下所示。

**示例#1:** 使用 [**numpy.std()**](https://www.geeksforgeeks.org/numpy-std-in-python/)

首先，我们创建一个字典。然后我们通过迭代将所有的值存储在一个列表中。在此之后，我们使用 NumPy 计算列表的标准偏差。

## 蟒蛇 3

```
# importing numpy
import numpy as np

# creating our test dictionary
dicti = {'a': 20, 'b': 32, 'c': 12, 'd': 93, 'e': 84}

# declaring an empty list
listr = []

# appending all the values in the list
for value in dicti.values():
    listr.append(value)

# calculating standard deviation using np.std
std = np.std(listr)

# printing results
print(std)
```

**输出:**

```
33.63569532505609  
```

**例 2:** 使用 [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

首先，我们使用循环从字典中创建一个值列表。然后我们计算平均值，方差，然后是标准差。

## 蟒蛇 3

```
# creating our test dictionary
dicti = {'a': 20, 'b': 32, 'c': 12, 'd': 93, 'e': 84}

# declaring an empty list
listr = []

# appending all the values in the list
for value in dicti.values():
    listr.append(value)

# Standard deviation of list
# Using sum() + list comprehension
mean = sum(listr) / len(listr)
variance = sum([((x - mean) ** 2) for x in listr]) / len(listr)
res = variance ** 0.5
print(res)
```

**输出:**

```
33.63569532505609  
```

**示例#3:** 使用 **pstdev()**

Pythons 内置的统计库提供了一个函数来计算给定列表的标准偏差。

## 蟒蛇 3

```
# importing the module
import statistics

# creating the test dictionary
dicti = {'a': 20, 'b': 32, 'c': 12, 'd': 93, 'e': 84}

# declaring an empty list
listr = []

# appending all the values in the list
for value in dicti.values():
    listr.append(value)

# Standard deviation of list
# Using pstdev()
res = statistics.pstdev(listr)
print(res)
```

**输出**:

```
33.63569532505609
```