# Python–从元组列表中提取数字

> 原文:[https://www . geesforgeks . org/python-从元组列表中提取数字/](https://www.geeksforgeeks.org/python-extract-digits-from-tuple-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要从元组列表中提取所有数字。这类问题可以在数据领域和日常编程中找到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(15，3)，(3，9)]
> **输出** : [9，5，3，1]
> 
> **输入** : test_list = [(15，3)]
> **输出**:【5，3，1】

**方法一:使用 map()+chain . from _ iterable()+set()+loop**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 chain.from_iterable()执行展平列表的任务，然后使用暴力方法提取数字。set()用于删除重复的数字。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract digits from Tuple list
# Using map() + chain.from_iterable() + set() + loop
from itertools import chain

# initializing list
test_list = [(15, 3), (3, 9), (1, 10), (99, 2)]

# printing original list
print("The original list is : " + str(test_list))

# Extract digits from Tuple list
# Using map() + chain.from_iterable() + set() + loop
temp = map(lambda ele: str(ele), chain.from_iterable(test_list))
res = set()
for sub in temp:
    for ele in sub:
        res.add(ele)

# printing result
print("The extracted digits : " + str(res))
```

**Output**

```py
The original list is : [(15, 3), (3, 9), (1, 10), (99, 2)]
The extracted digits : {'1', '0', '3', '2', '9', '5'}
```

**方法#2:使用正则表达式**
这是执行这个任务的另一种方式。在这种情况下，使用适当的正则表达式来提取所需的唯一数字。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract digits from Tuple list
# Using regex expression
import re

# initializing list
test_list = [(15, 3), (3, 9), (1, 10), (99, 2)]

# printing original list
print("The original list is : " + str(test_list))

# Extract digits from Tuple list
# Using regex expression
temp = re.sub(r'[\[\]\(\), ]', '', str(test_list))
res = [int(ele) for ele in set(temp)]

# printing result
print("The extracted digits : " + str(res))
```

**Output**

```py
The original list is : [(15, 3), (3, 9), (1, 10), (99, 2)]
The extracted digits : [5, 9, 2, 0, 1, 3]
```