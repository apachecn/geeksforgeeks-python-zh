# 在 Python 中声明一个空列表

> 原文:[https://www . geesforgeks . org/declare-a-a-empty-list-in-python/](https://www.geeksforgeeks.org/declare-an-empty-list-in-python/)

[列表](https://www.geeksforgeeks.org/python-list/)就像用其他语言声明的数组一样。列表**不必总是同质化的**，这使得它成为 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中最强大的工具。单个列表可能包含整数、字符串和对象等数据类型。列表是可变的，因此，即使在创建之后，它们也可以被更改。

然而，你有没有想过如何在 Python 中声明一个空列表？这可以通过两种方式实现，即使用`square brackets[]`或使用`list()` 构造函数。

**使用方括号`[]`**
Python 中的列表可以通过将序列放在方括号`[]`中来创建。要声明一个空列表，只需分配一个带方括号的变量。

**示例:**

```py
# Python program to declare
# empty list

# list is declared
a = []         

print("Values of a:", a)
print("Type of a:", type(a))
print("Size of a:", len(a))     
```

**输出:**

```py
Values of a: []
Type of a: <class 'list'>
Size of a: 0

```

**使用列表()构造函数**
`list()`构造函数用于在 Python 中创建列表。

> **语法:**列表([可迭代])
> 
> **参数:**
> **可迭代:**这是一个可选参数，可以是序列(字符串、元组)或集合(字典、集合)或迭代器对象。
> 
> **返回类型:**
> 
> *   如果没有传递参数，则返回一个空列表。
> *   如果传递了一个参数，那么它会返回一个 iterable 中的元素列表。

**示例:**

```py
# Python program to create
# empty list

# list is declared
a = list()  

print("Values of a:", a)
print("Type of a:", type(a))
print("Size of a:", len(a))     
```

**输出:**

```py
Values of a: []
Type of a: <class 'list'>
Size of a: 0

```