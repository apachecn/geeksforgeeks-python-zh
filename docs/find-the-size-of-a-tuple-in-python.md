# 在 Python 中找到元组的大小

> 原文:[https://www . geesforgeks . org/find-the-size-of-tuple-in-python/](https://www.geeksforgeeks.org/find-the-size-of-a-tuple-in-python/)

[Tuple](https://www.geeksforgeeks.org/python-tuples/) 是 Python 对象的集合，很像一个列表。存储在元组中的值序列可以是任何类型，并且它们由整数索引。
元组的值在语法上用“逗号”分隔。虽然这不是必需的，但是通过在括号中结束值序列来定义元组更常见。
元组的大小是指元组对象占用的内存量(以字节为单位)。在本文中，我们将学习获得 python Tuple 大小的各种方法。

**1。使用`getsizeof()`功能:**

`getsizeof()`函数属于 python 的 sys 模块。它已在下面的示例中实现。

**例 1:**

```
import sys

# sample Tuples
Tuple1 = ("A", 1, "B", 2, "C", 3)
Tuple2 = ("Geek1", "Raju", "Geek2", "Nikhil", "Geek3", "Deepanshu")
Tuple3 = ((1, "Lion"), ( 2, "Tiger"), (3, "Fox"), (4, "Wolf"))

# print the sizes of sample Tuples
print("Size of Tuple1: " + str(sys.getsizeof(Tuple1)) + "bytes")
print("Size of Tuple2: " + str(sys.getsizeof(Tuple2)) + "bytes")
print("Size of Tuple3: " + str(sys.getsizeof(Tuple3)) + "bytes")
```

**输出:**

```
Size of Tuple1: 96bytes
Size of Tuple2: 96bytes
Size of Tuple3: 80bytes
```

**注意:**`sys.getsizeof()`函数包含边际空间使用，其中包含对象的垃圾收集开销。这意味着除了正在使用的空间的垃圾收集开销之外，它还返回对象占用的总空间。

**1。使用内置的`__sizeof__()`方法:**

Python 还有一个内置的 __sizeof__()方法来确定对象的空间分配，而没有任何额外的垃圾值。它已在下面的示例中实现。
**例 2:**

```
# sample Tuples
Tuple1 = ("A", 1, "B", 2, "C", 3)
Tuple2 = ("Geek1", "Raju", "Geek2", "Nikhil", "Geek3", "Deepanshu")
Tuple3 = ((1, "Lion"), ( 2, "Tiger"), (3, "Fox"), (4, "Wolf"))

# print the sizes of sample Tuples
print("Size of Tuple1: " + str(Tuple1.__sizeof__()) + "bytes")
print("Size of Tuple2: " + str(Tuple2.__sizeof__()) + "bytes")
print("Size of Tuple3: " + str(Tuple3.__sizeof__()) + "bytes")
```

**输出:**

```
Size of Tuple1: 72bytes
Size of Tuple2: 72bytes
Size of Tuple3: 56bytes
```