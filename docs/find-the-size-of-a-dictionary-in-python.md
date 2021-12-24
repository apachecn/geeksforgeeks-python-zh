# 在 Python 中找到字典的大小

> 原文:[https://www . geesforgeks . org/find-the-size-a-in-dictionary-python/](https://www.geeksforgeeks.org/find-the-size-of-a-dictionary-in-python/)

[Python 中的 Dictionary](https://www.geeksforgeeks.org/python-dictionary/)是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 key:value pair。字典中提供了键值，以使其更加优化。字典的大小是指字典对象占用的内存量(以字节为单位)。在本文中，我们将学习获得 python 字典大小的各种方法。

**1。使用`getsizeof()`功能:**

`getsizeof()`函数属于 python 的 sys 模块。它已在下面的示例中实现。

**例 1:**

```py
import sys

# sample Dictionaries
dic1 = {"A": 1, "B": 2, "C": 3} 
dic2 = {"Geek1": "Raju", "Geek2": "Nikhil", "Geek3": "Deepanshu"}
dic3 = {1: "Lion", 2: "Tiger", 3: "Fox", 4: "Wolf"}

# print the sizes of sample Dictionaries
print("Size of dic1: " + str(sys.getsizeof(dic1)) + "bytes")
print("Size of dic2: " + str(sys.getsizeof(dic2)) + "bytes")
print("Size of dic3: " + str(sys.getsizeof(dic3)) + "bytes")
```

**输出:**

```py
Size of dic1: 216bytes
Size of dic2: 216bytes
Size of dic3: 216bytes
```

**1。使用内置的`__sizeof__()`方法:**

Python 还有一个内置的 __sizeof__()方法来确定对象的空间分配，而没有任何额外的垃圾值。它已在下面的示例中实现。
**例 2:**

```py
# sample Dictionaries
dic1 = {"A": 1, "B": 2, "C": 3} 
dic2 = {"Geek1": "Raju", "Geek2": "Nikhil", "Geek3": "Deepanshu"}
dic3 = {1: "Lion", 2: "Tiger", 3: "Fox", 4: "Wolf"}

# print the sizes of sample Dictionaries
print("Size of dic1: " + str(dic1.__sizeof__()) + "bytes")
print("Size of dic2: " + str(dic2.__sizeof__()) + "bytes")
print("Size of dic3: " + str(dic3.__sizeof__()) + "bytes")
```

**输出:**

```py
Size of dic1: 216bytes
Size of dic2: 216bytes
Size of dic3: 216bytes
```