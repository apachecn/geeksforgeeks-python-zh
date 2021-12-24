# Python–矩阵中的字符坐标

> 原文:[https://www . geesforgeks . org/python-字符-矩阵中的坐标/](https://www.geeksforgeeks.org/python-character-coordinates-in-matrix/)

有时候，在处理 Python 数据时，我们会遇到一个问题，我们需要提取 Matrix 中的所有坐标，这些坐标都是字符。这类问题可能在诸如 web 开发和日常编程等领域有潜在的应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = ['1G '，' 12F '，' 231G']
> **输出** : [(0，1)，(1，2)，(2，3)]
> 
> **输入** : test_list = ['G '，' F '，' G']
> **输出** : [(0，0)，(1，0)，(2，0)]

**方法#1:使用`enumerate() + list comprehension + isalpha()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 enumerate 执行索引工作，使用 isalpha()完成字符过滤。

```
# Python3 code to demonstrate working of 
# Character coordinates in Matrix
# Using enumerate() + list comprehension + isalpha()

# initializing list
test_list = ['23f45.;4d', '5678d56d', '789', '5678g']

# printing original list
print("The original list is : " + str(test_list))

# Character coordinates in Matrix
# Using enumerate() + list comprehension + isalpha()
res = [(x, y) for x, val in enumerate(test_list) 
        for y, chr in enumerate(val) if chr.isalpha()]  

# printing result 
print("Character indices : " + str(res)) 
```

**Output :**

```
The original list is : ['23f45.;4d', '5678d56d', '789', '5678g']
Character indices : [(0, 2), (0, 8), (1, 4), (1, 7), (3, 4)]

```

**方法 2:使用`regex()` +循环**
以上功能的组合可以解决这个问题。在本文中，我们使用正则表达式执行过滤字母的任务。只返回每个字符串中第一个出现的字符。

```
# Python3 code to demonstrate working of 
# Character coordinates in Matrix
# Using regex() + loop
import re

# initializing list
test_list = ['23f45.;4d', '5678d56d', '789', '5678g']

# printing original list
print("The original list is : " + str(test_list))

# Character coordinates in Matrix
# Using regex() + loop
res = []
for key, val in enumerate(test_list):
    temp = re.search('([a-zA-Z]+)', val)
    if temp :
        res.append((key, temp.start()))

# printing result 
print("Character indices : " + str(res)) 
```

**Output :**

```
The original list is : ['23f45.;4d', '5678d56d', '789', '5678g']
Character indices : [(0, 2), (1, 4), (3, 4)]

```