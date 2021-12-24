# 找到列表的大小–Python

> 原文:[https://www . geesforgeks . org/find-the-size-a-list-python/](https://www.geeksforgeeks.org/find-the-size-of-a-list-python/)

在 Python 中，[列表](https://www.geeksforgeeks.org/python-list/)是一种集合数据类型，可以以有序的方式存储元素，也可以有重复的元素。列表的大小意味着列表对象占用的内存量(以字节为单位)。在本文中，我们将学习获得 python 列表大小的各种方法。

**1。使用`getsizeof()`功能:**

`getsizeof()`函数属于 python 的 sys 模块。它已在下面的示例中实现。

**例 1:**

```
import sys

# sample lists
list1 = [1, 2, 3, 5]
list2 = ["GeeksForGeeks", "Data Structure", "Algorithms"]
list3 = [1, "Geeks", 2, "For", 3, "Geeks"]

# print the sizes of sample lists
print("Size of list1: " + str(sys.getsizeof(list1)) + "bytes")
print("Size of list2: " + str(sys.getsizeof(list2)) + "bytes")
print("Size of list3: " + str(sys.getsizeof(list3)) + "bytes")
```

**输出:**

```
Size of list1: 96bytes
Size of list1: 88bytes
Size of list1: 112bytes
```

**注意:**`sys.getsizeof()`函数包含边际空间使用，其中包含对象的垃圾收集开销。这意味着除了正在使用的空间的垃圾收集开销之外，它还返回对象占用的总空间。

**1。使用内置的`__sizeof__()`方法:**

Python 还有一个内置的 __sizeof__()方法来确定对象的空间分配，而没有任何额外的垃圾值。它已在下面的示例中实现。
**例 2:**

```
# sample lists
list1 = [1, 2, 3, 5]
list2 = ["GeeksForGeeks", "Data Structure", "Algorithms"]
list3 = [1, "Geeks", 2, "For", 3, "Geeks"]

# print the sizes of the sample lists
print("Size of list1: " + str(list1.__sizeof__()) + "bytes")
print("Size of list2: " + str(list2.__sizeof__()) + "bytes")
print("Size of list3: " + str(list3.__sizeof__()) + "bytes")
```

**输出:**

```
Size of list1: 72bytes
Size of list1: 64bytes
Size of list1: 88bytes
```