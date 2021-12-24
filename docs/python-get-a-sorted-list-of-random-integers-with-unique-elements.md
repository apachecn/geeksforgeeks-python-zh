# Python–获取具有唯一元素的随机整数的排序列表

> 原文:[https://www . geesforgeks . org/python-get-一个带有唯一元素的随机整数排序列表/](https://www.geeksforgeeks.org/python-get-a-sorted-list-of-random-integers-with-unique-elements/)

给定下限和上限，从开始到结束，生成具有唯一元素的随机数排序列表。

**例:**

```
Input: num = 10, start = 100, end = 200
Output: [102, 118, 124, 131, 140, 148, 161, 166, 176, 180]

Input: num = 5, start = 1, end = 100
Output: [37, 49, 64, 84, 95]

```

在 Python 中生成随机数，使用`random`模块的`randint()`功能。

**语法:**

```
randint(start, end)

```

`randint()`接受两个参数:起点和终点。两者都应该是整数，第一个值应该总是小于第二个值。

下面是实现。

```
# Python program to create 
# a sorted list of unique random 
# numbers

import random

# Function to generate a sorted list  
# of random numbers in a given
# range with unique elements
def createRandomSortedList(num, start = 1, end = 100):
    arr = []
    tmp = random.randint(start, end)

    for x in range(num):

        while tmp in arr:
            tmp = random.randint(start, end)

        arr.append(tmp)

    arr.sort()

    return arr

# Driver's code
print(createRandomSortedList(10, 100, 200))
print(createRandomSortedList(5)))
```

**输出:**

```
[102, 118, 124, 131, 140, 148, 161, 166, 176, 180]
[37, 49, 64, 84, 95]

```