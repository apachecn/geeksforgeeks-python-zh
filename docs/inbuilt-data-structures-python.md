# Python 中的内置数据结构

> 原文:[https://www . geeksforgeeks . org/内置-数据结构-python/](https://www.geeksforgeeks.org/inbuilt-data-structures-python/)

Python 有四种基本的内置数据结构，即列表、字典、元组和集合。这些几乎涵盖了我们现实世界数据结构的 80%。本文将涵盖上述主题。

上述主题分为以下四个部分。

**列表:**Python 中的列表是可用的最通用的集合对象类型之一。另外两种类型是字典和元组，但它们更像是列表的变体。

*   Python 列表完成了其他语言中大多数集合数据结构的工作，由于它们是内置的，所以您不必担心手动创建它们。
*   列表可以用于任何类型的对象，从数字和字符串到更多列表。
*   它们就像字符串一样被访问(例如，切片和连接)，所以它们使用起来很简单，并且长度可变，也就是说，它们在使用时会自动增长和收缩。
*   实际上，Python 列表是 Python 解释器中的 C 数组，就像指针数组一样。

**字典:**在 python 中，字典类似于其他语言中的 hash 或 map。它由键值对组成。该值可以通过字典中的唯一键来访问。

*   键是唯一且不可变的对象。

语法:

```
dictionary = {"key name": value}
```

**元组:** Python 元组的工作方式与 Python 列表完全一样，只是它们是不可变的，即它们不能被
原地更改。它们通常写在括号内，以区别于列表(使用方括号)，但正如您将看到的，括号并不总是必要的。因为元组是不可变的，所以它们的长度是固定的。要增加或缩小元组，必须创建一个新的元组。

**以下是常用元组列表:**

```
() An empty tuple
t1 = (0, ) A one-item tuple (not an expression)
t2 = (0, 1, 2, 3) A four-item tuple
t3 = 0, 1, 2, 3 Another four-item tuple (same as prior line, just minus the parenthesis)
t3 = (‘abc’, (‘def’, ‘ghi’)) Nested tuples
t1[n], t3[n][j] Index
t1[i:j], Slice
len(tl) Length
```

## 蟒蛇 3

```
# Python program to illustrate
# tuple
tup = (1, "a", "string", 1+2)
print (tup)
print (tup[1])
```

**输出:**

```
(1, 'a', 'string', 3)
a
```

[Python 中元组的详细文章](https://www.geeksforgeeks.org/tuples-in-python/)

**集合:**唯一对象的无序集合。

*   集合运算，如并集(|)、交集(&)、差集(-)，可以应用于集合。
*   [冻结集](https://www.geeksforgeeks.org/frozenset-in-python/)是不可变的，即一旦创建，就不能向其中添加更多数据
*   {}用于表示集合。放在这些括号内的对象将被视为一个集合。

## 计算机编程语言

```
# Python program to demonstrate working of
# Set in Python

# Creating two sets
set1 = set()
set2 = set()

# Adding elements to set1
for i in range(1, 6):
    set1.add(i)

# Adding elements to set2
for i in range(3, 8):
    set2.add(i)

print("Set1 = ", set1)
print("Set2 = ", set2)
print("\n")
```

**输出:**

```
('Set1 = ', set([1, 2, 3, 4, 5]))
('Set2 = ', set([3, 4, 5, 6, 7]))
```

要阅读更多关于 python 中集合的内容，请阅读我们关于集合的文章 [<u>点击此处。</u>](https://www.geeksforgeeks.org/sets-in-python/)