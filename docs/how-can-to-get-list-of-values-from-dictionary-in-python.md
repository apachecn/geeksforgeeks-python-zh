# 如何在 Python 中从字典中获取值列表？

> 原文:[https://www . geesforgeks . org/如何从 python 字典中获取值列表/](https://www.geeksforgeeks.org/how-can-to-get-list-of-values-from-dictionary-in-python/)

在本文中，我们将讨论如何使用 Python 从字典中获取值列表。

## 方法 1:使用 list()函数

我们可以使用 dictionary.values()和 list()函数来获取列表。这里，values()方法是一个字典方法，用于从 key:value 对中访问值，然后我们使用 list()函数将这些值转换为 list

**语法**:

```py
list(dictionary.values())
```

**示例** : Python 程序，创建以学生姓名为关键字、数值为主题的字典

## 蟒蛇 3

```py
# create a dictionary
# with student names as key
# values as subjects
data = {'manoja': 'java', 'tripura': 'python',
        'manoj': 'statistics', 'manoji': 'cpp'}

# get list of values
list(data.values())
```

**输出**:

```py
['java', 'python', 'statistics', 'cpp']
```

## 方法 2:使用[]

我们可以使用[]和*来获取字典值的所有列表。这里 values()是一个字典方法，用于从 key:value 对中获取值，而*用于仅获取值，而不是获取 dict_values，然后我们使用 list()函数进入一个列表

**语法**:

```py
[*dictionary.values()]
```

**例**:

## 蟒蛇 3

```py
# create a dictionary
# with student names as key
# values as subjects
data = {'manoja': 'java', 'tripura': 'python',
        'manoj': 'statistics', 'manoji': 'cpp'}

# get list of values
[*data.values()]
```

**输出:**

## 方法三:使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

使用列表理解，我们可以得到字典值的列表。这里我们使用列表理解，通过迭代器在字典中进行迭代。这将返回键:值对中的每个值。

**语法:**

```py
[dictionary[i] for i in dictionary]
```

**例**:

## 蟒蛇 3

```py
# create a dictionary
# with student names as key
# values as subjects
data = {'manoja': 'java', 'tripura': 'python',
        'manoj': 'statistics', 'manoji': 'cpp'}

# get list of values using comprehension
[data[i] for i in data]
```

**输出**:

```py
['java', 'python', 'statistics', 'cpp']
```