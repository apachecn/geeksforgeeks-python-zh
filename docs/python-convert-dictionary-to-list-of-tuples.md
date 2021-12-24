# Python |将字典转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-to-list-of-tuples/](https://www.geeksforgeeks.org/python-convert-dictionary-to-list-of-tuples/)

给定一个字典，编写一个 Python 程序，将给定的字典转换成元组列表。
**例:**

```py
Input: { 'Geeks': 10, 'for': 12, 'Geek': 31 }
Output : [ ('Geeks', 10), ('for', 12), ('Geek', 31) ]

Input: { 'dict': 11, 'to': 22, 'list_of_tup': 33}
Output : [ ('dict', 11), ('to', 22), ('list_of_tup', 33) ]
```

下面是将字典转换为元组列表的各种方法。
**方法#1 :** 使用列表理解

## 蟒蛇 3

```py
# Python code to convert dictionary into list of tuples

# Initialization of dictionary
dict = { 'Geeks': 10, 'for': 12, 'Geek': 31 }

# Converting into list of tuple
list = [(k, v) for k, v in dict.items()]

# Printing list of tuple
print(list)
```

**Output:** 

```py
[('Geek', 31), ('for', 12), ('Geeks', 10)]
```