# 在 Python 中将对象转换为字符串

> 原文:[https://www . geesforgeks . org/convert-object-to-string-in-python/](https://www.geeksforgeeks.org/convert-object-to-string-in-python/)

Python 定义了类型转换函数，直接将一种数据类型转换成另一种数据类型。本文旨在提供有关将对象转换为字符串的信息。

## 将对象转换为字符串

在 Python 中，一切都是一个对象。因此，所有内置对象都可以使用 str()和 repr()方法转换为字符串。

**实施例 1:** 使用 str()方法

## 蟒蛇 3

```
# object of int
Int = 6

# object of float
Float = 6.0

# Converting to string
s1 = str(Int)
print(s1)
print(type(s1))

s2= str(Float)
print(s2)
print(type(s2))
```

**输出:**

```
6
<class 'str'>
6.0
<class 'str'>
```

**示例 2:** 使用 repr()将对象转换为字符串

## python 3

```
print(repr({"a": 1, "b": 2}))
print(repr([1, 2, 3]))

# Custom class
class C():
    def __repr__(self):
        return "This is class C"

# Converting custom object to 
# string
print(repr(C()))
```

**输出:**

```
{'a': 1, 'b': 2}
[1, 2, 3]
This is class C
```

**注意:**要了解 str()和 repr()的更多信息以及它们之间的区别，请参考 Python 中的 [str() vs repr()](https://www.geeksforgeeks.org/str-vs-repr-in-python/)