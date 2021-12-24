# 【_ _ sizeof _ _()和 getsizeof()方法的区别–Python

> 原文:[https://www . geesforgeks . org/difference-sizeof _ _-和-getsizeof-method-python/](https://www.geeksforgeeks.org/difference-between-__sizeof__-and-getsizeof-method-python/)

当我们编写大块代码时，内存管理是重中之重。所以除了良好的编码知识外，能够编写程序也很重要，这样才能高效处理内存。

因此，让我们看看 Python 中获取特定对象大小的两种方法。这是 getsizeof()方法和 __sizeof()方法。
getsizeof()是一个系统特定的方法，因此我们必须导入 sys 模块来使用它。计算列表大小的示例代码如下所示。

## 蟒蛇 3

```py
import sys
a =[1, 2]
b =[1, 2, 3, 4]
c =[1, 2, 3, 4]
d =[2, 3, 1, 4, 66, 54, 45, 89]
print(sys.getsizeof(a))
print(sys.getsizeof(b))
print(sys.getsizeof(c))
print(sys.getsizeof(d))
```

**输出:**

```py
80
96
96
128
```

getsizeof()方法调用对象的 __sizeof__()方法，会产生额外的垃圾收集器开销。因此，getsize()方法返回的大小将大于 __sizeof()__ 方法返回的大小。
例如，getsizeof()方法为空列表返回 64 个字节，然后为每个附加元素返回 8 个字节。
现在我们来看看 **__sizeof__()** 法。它返回对象的大小，没有任何开销。

## 蟒蛇 3

```py
w =[1, 2]
x =[4, 5, 7, 9]
y =[2, 8, 6, 56, 45, 89, 88]
z =[54, 45, 12, 23, 24, 90, 20, 40]
print(w.__sizeof__())
print(x.__sizeof__())
print(y.__sizeof__())
print(z.__sizeof__())
```

**输出:**

```py
56
72
96
104
```

例如，__sizeof__()方法为空列表返回 40 个字节，然后为每个附加元素返回 8 个字节。