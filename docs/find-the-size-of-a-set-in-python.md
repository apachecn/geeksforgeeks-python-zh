# 在 Python 中找到集合的大小

> 原文:[https://www . geesforgeks . org/find-the-size-in-set-python/](https://www.geeksforgeeks.org/find-the-size-of-a-set-in-python/)

一个[集合](https://www.geeksforgeeks.org/sets-in-python/)是一个无序的集合数据类型，它是可迭代的，可变的，并且没有重复的元素。Python 的集合类代表了集合的数学概念。集合的大小是指集合对象占用的内存量(以字节为单位)。在本文中，我们将学习获得 python 集大小的各种方法。

**1。使用`getsizeof()`功能:**

`getsizeof()`函数属于 python 的 sys 模块。它已在下面的示例中实现。

**例 1:**

```py
import sys

# sample Sets
Set1 = {"A", 1, "B", 2, "C", 3}
Set2 = {"Geek1", "Raju", "Geek2", "Nikhil", "Geek3", "Deepanshu"}
Set3 = {(1, "Lion"), ( 2, "Tiger"), (3, "Fox")}

# print the sizes of sample Sets
print("Size of Set1: " + str(sys.getsizeof(Set1)) + "bytes")
print("Size of Set2: " + str(sys.getsizeof(Set2)) + "bytes")
print("Size of Set3: " + str(sys.getsizeof(Set3)) + "bytes")
```

输出:

```py
Size of Set1: 736bytes
Size of Set2: 736bytes
Size of Set3: 224bytes
```

**注意:**`sys.getsizeof()`函数包含边际空间使用，其中包含对象的垃圾收集开销。这意味着除了正在使用的空间的垃圾收集开销之外，它还返回对象占用的总空间。

**1。使用内置的`__sizeof__()`方法:**

Python 还有一个内置的 __sizeof__()方法来确定对象的空间分配，而没有任何额外的垃圾值。它已在下面的示例中实现。
**例 2:**

```py
import sys

# sample Sets
Set1 = {"A", 1, "B", 2, "C", 3}
Set2 = {"Geek1", "Raju", "Geek2", "Nikhil", "Geek3", "Deepanshu"}
Set3 = {(1, "Lion"), ( 2, "Tiger"), (3, "Fox")}

# print the sizes of sample Sets
print("Size of Set1: " + str(Set1.__sizeof__()) + "bytes")
print("Size of Set2: " + str(Set2.__sizeof__()) + "bytes")
print("Size of Set3: " + str(Set3.__sizeof__()) + "bytes")
```

**输出:**

```py
Size of Set1: 712bytes
Size of Set2: 712bytes
Size of Set3: 200bytes
```