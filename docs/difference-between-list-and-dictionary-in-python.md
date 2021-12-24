# Python 中列表和字典的区别

> 原文:[https://www . geesforgeks . org/python 中列表和字典的区别/](https://www.geeksforgeeks.org/difference-between-list-and-dictionary-in-python/)

[列表](https://www.geeksforgeeks.org/python-list/)就像用其他语言声明的数组一样。列表不必总是同质的，这使得它成为 Python 中最强大的工具。单个列表可能包含整数、字符串和对象等数据类型。列表是可变的，因此，即使在创建之后，它们也可以被更改。
**例:**

## 蟒蛇 3

```py
# Python program to demonstrate
# Lists

# Creating a List with
# the use of multiple values
List = ["Geeks", "For", "Geeks"]
print("List containing multiple values: ")
print(List[0]) 
print(List[2])

# Creating a Multi-Dimensional List
# (By Nesting a list inside a List)
List = [['Geeks', 'For'] , ['Geeks']]
print("\nMulti-Dimensional List: ")
print(List)
```

**输出:**

```py
List containing multiple values: 
Geeks
Geeks

Multi-Dimensional List: 
[['Geeks', 'For'], ['Geeks']]
```

[另一方面，Python 中的 Dictionary](https://www.geeksforgeeks.org/python-dictionary/) 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 key:value pair。字典中提供了键值，以使其更加优化。字典中的每个键值对由冒号分隔，而每个键由“逗号”分隔。
**例:**

## 蟒蛇 3

```py
# Python program to demonstrate
# dictionary

# Creating a Dictionary 
# with Integer Keys
Dict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}
print("Dictionary with the use of Integer Keys: ")
print(Dict)

# Creating a Dictionary 
# with Mixed keys
Dict = {'Name': 'Geeks', 1: [1, 2, 3, 4]}
print("\nDictionary with the use of Mixed Keys: ")
print(Dict)
```

**输出:**

```py
Dictionary with the use of Integer Keys: 
{1: 'Geeks', 2: 'For', 3: 'Geeks'}

Dictionary with the use of Mixed Keys: 
{1: [1, 2, 3, 4], 'Name': 'Geeks'}
```

#### 列表和词典的区别:

<figure class="table">

| 目录 | 词典 |
| --- | --- |
| List 是索引值对的集合，就像 c++中的数组一样。 | 字典是**键和值**对的散列结构。 |
| 列表是通过将元素放在由逗号“，”分隔的 **[ ]** 中创建的 | 字典是通过将 **{ }** 中的元素作为“键”来创建的:“值”，每个键值对用逗号“，” |
| 列表的索引是从 0 开始的整数。 | 字典的关键字可以是任何数据类型。 |
| 元素通过索引访问。 | 元素是通过键值访问的。 |
| 输入元素的顺序保持不变。 | 维持秩序没有保障。 |

</figure>

#### 时空权衡

使用字典查找元素更有效，因为在字典中遍历比使用列表花费的时间更少。
例如，让我们考虑一个依赖于数据检索速度的机器学习模型中有 5000000 个元素的数据集。为了实现这一点，我们必须明智地在两种数据结构之间进行选择，即列表和字典。由于字典是以 python3.6 中的散列表的形式实现的，因此字典是首选的，因为它的时间和空间存储更少，所以在字典中它从来都不是一个时空权衡的问题。
**例 1:**

## 蟒蛇 3

```py
# Program to demonstrate
# space-time trade-off between
# dictionary and list

# To calculate the time
# difference
import time

# Creating a dictionary
d ={'john':1, 'alex':2}

x = time.time()

# Accessing elements
print("Accessing dictionary elements:")
for key in d:
    print(d[key], end=" ")

y = time.time()
print("\nTime taken by dictionary:", y-x)

# Creating a List
c =[1, 2]

x = time.time()

print("\nAccessing List elements:")
for i in c:
    print(i, end=" ")

y = time.time()
print("\nTime taken by dictionary:", y-x)
```

**输出:**

```py
Accessing dictionary elements:
1 2 
Time taken by dictionary: 1.0013580322265625e-05

Accessing List elements:
1 2 
Time taken by dictionary: 3.5762786865234375e-06
```

**例 2:**

## 蟒蛇 3

```py
# Program to fetch particular
# elements of structure

import time

# Creating dictionary and list
dict_name ={"bob":12, "john":11}
list_name =[2, 3, 4, 5, 1]

# Time taken by dictionary
x = time.time()
L = dict_name["bob"]
y = time.time()
print("Time taken by dictionary:", y-x)

# Time taken by list
x = time.time()
L = list_name[2]
y = time.time()
print("\nTime taken by list:", y-x)
```

**输出:**

```py
Time taken by dictionary: 9.5367431640625e-07

Time taken by list: 4.76837158203125e-07
```

**注意:**从列表中提取单个元素比从字典中提取要花费更多的时间，因为字典使用哈希表来实现这种排列。