# Python–构建等级列表

> 原文:[https://www.geeksforgeeks.org/python-construct-grades-list/](https://www.geeksforgeeks.org/python-construct-grades-list/)

给定一个数字，构造一个包含前 N 个字符的所有可能等级组合的列表。

> **输入** : num = 3
> **输出** : ['A+'，' A '，' A-'，' B+ '，' B '，' B- '，' C+'，' C '，' C-']
> **说明**:列表中渲染到 C 的所有等级。
> **输入** : num = 5
> **输出** : ['A+'，' A '，' A-'，' B+ '，' B '，' B- '，' C+'，' C '，' C-'，' D+'，' D-'，' E+'，' E '，' E-']
> **解释** : 5 对应 E，遂全组合。

**方法#1:使用列表理解+order()**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 order()执行递增和提取 ascii 字符的任务，并且在字符列表创建中使用列表理解。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Construct Grades List
# Using list comprehension + ord()

# initializing N
num = 4

# Using list comprehension + ord()
# each character paired to symbols and character incremented using idx
# conversion by chr + ord
res =  [chr(ord('A') + idx) + sym for idx in range(num)
       for sym in ['+', '', '-']]      

# printing result
print("Grades List : " + str(res))
```

**Output : **

```py
Grades List : ['A+', 'A', 'A-', 'B+', 'B', 'B-', 'C+', 'C', 'C-', 'D+', 'D', 'D-']
```

**方法 2:使用 join()+map()+product()+ascii _ 大写**
以上函数的组合可以用来解决这个问题。在本例中，我们使用 ascii _ 大写、product()和 map()执行提取 ascii 字符的任务，用于执行与符号的链接，结果是在执行所有连接之后创建的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Construct Grades List
# Using join() + map() + product() + ascii_uppercase
from string import ascii_uppercase
from itertools import product

# initializing N
num = 4

# Using join() + map() + product() + ascii_uppercase
# pairing using product, map used to join characters with symbols.
res = [*map(''.join, product(ascii_uppercase[:num], ['+', '', '-']))]

# printing result
print("Grades List : " + str(res))
```

**Output : **

```py
Grades List : ['A+', 'A', 'A-', 'B+', 'B', 'B-', 'C+', 'C', 'C-', 'D+', 'D', 'D-']
```