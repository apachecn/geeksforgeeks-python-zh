# Python |生成给定范围内的随机数并存储在列表中

> 原文:[https://www . geesforgeks . org/python-在给定范围内生成随机数并将其存储在列表中/](https://www.geeksforgeeks.org/python-generate-random-numbers-within-a-given-range-and-store-in-a-list/)

给定下限和上限，在给定范围内生成给定数量的随机数，从“开始”到“结束”开始，并将它们存储在列表中。
示例:

```py
Input : num = 10, start = 20, end = 40
Output : [23, 20, 30, 33, 30, 36, 37, 27, 28, 38]
The output contains 10 random numbers in
range [20, 40].

Input : num = 5, start = 10, end = 15
Output : [15, 11, 15, 12, 11]
The output contains 5 random numbers in
range [10, 15].
```

Python 提供了一个随机模块来生成随机数。为了生成随机数，我们使用了随机函数和 randint 函数。
**语法:**

```py
randint(start, end)
```

randint 接受两个参数:起点和终点。两者都应该是整数，第一个值应该总是小于第二个值。

## 蟒蛇 3

```py
# Python code to generate
# random numbers and
# append them to a list
import random

# Function to generate
# and append them
# start = starting range,
# end = ending range
# num = number of
# elements needs to be appended
def Rand(start, end, num):
    res = []

    for j in range(num):
        res.append(random.randint(start, end))

    return res

# Driver Code
num = 10
start = 20
end = 40
print(Rand(start, end, num))
```

输出:

```py
[23, 20, 30, 33, 30, 36, 37, 27, 28, 38]
```

**方法二:**使用 numpy [random.randint()](https://www.geeksforgeeks.org/python-randint-function/) 方法生成 random 数。

## 蟒蛇 3

```py
# Python code to generate
# random numbers and
# append them to a list
import numpy as np
def Rand(start, end, num):
    res = []

    for j in range(num):
        res.append(np.random.randint(start, end))

    return res

# Driver Code
num = 10
start = 20
end = 40
print(Rand(start, end, num))
```

**输出:**

```py
[30, 30, 38, 39, 39, 37, 24, 25, 28, 32]
```