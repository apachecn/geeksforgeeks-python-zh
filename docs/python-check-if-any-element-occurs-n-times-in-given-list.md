# Python |检查给定列表中是否有任何元素出现了 n 次

> 原文:[https://www . geesforgeks . org/python-检查给定列表中是否有任何元素出现 n 次/](https://www.geeksforgeeks.org/python-check-if-any-element-occurs-n-times-in-given-list/)

给定一个列表，任务是找出在给定的整数列表中是否有任何元素出现了 n 次。它将基本上检查出现 n 次的第一个元素。
**例:**

```py
Input: l =  [1, 2, 3, 4, 0, 4, 3, 2, 1, 2], n = 3
Output :  2

Input: l =  [1, 2, 3, 4, 0, 4, 3, 2, 1, 2, 1, 1], n = 4
Output :  1

```

下面是 Python 中完成任务的一些方法–
**方法 1:使用简单迭代和排序**

## 蟒蛇 3

```py
# Python code to find occurrence of any element
# appearing 'n' times

# Input Initialisation
input = [1, 2, 3, 0, 4, 3, 4, 0, 0]

# Sort Input
input.sort()

# Constants Declaration
n = 3
prev = -1
count = 0
flag = 0

# Iterating
for item in input:
    if item == prev:
        count = count + 1
    else:
        count = 1
    prev = item

    if count == n:
        flag = 1
        print("There are {} occurrences of {} in {}".format(n, item, input))
        break

# If no element is not found.
if flag == 0:
    print("No occurrences found")
```

**输出:**

```py
There are 3 occurrences of 0 in [0, 0, 0, 1, 2, 3, 3, 4, 4]

```

**方法二:使用**计数

## 蟒蛇 3

```py
# Python code to find occurrence of any element
# appearing 'n' times

# Input list initialisation
input = [1, 2, 3, 4, 0, 4, 3, 4]

# Constant declaration
n = 3

# print
print("There are {} occurrences of {} in {}".format(input.count(n), n, input))
```

**输出:**

```py
There are 2 occurrences of 3 in [1, 2, 3, 4, 0, 4, 3, 4]

```

**方法 3:使用 defaultdict**
我们首先在字典中填充列表项，然后我们发现任何元素的计数是否等于 n.

## 蟒蛇 3

```py
# Python code to find occurrence of any element
# appearing 'n' times

# importing
from collections import defaultdict

# Dictionary declaration
dic = defaultdict(int)

# Input list initialisation
Input = [9, 8, 7, 6, 5, 9, 2]

# Dictionary populate
for i in Input:
    dic[i]+= 1

# constant declaration
n = 2
flag = 0

# Finding from dictionary
for element in Input:
    if element in dic.keys() and dic[element] == n:
        print("Yes, {} has {} occurrence in {}.".format(element, n, Input))
        flag = 1
        break

# if element not found.
if flag == 0:
    print("No occurrences found")
```

**输出:**

```py
Yes, 9 has 2 occurrence in [9, 8, 7, 6, 5, 9, 2]

```