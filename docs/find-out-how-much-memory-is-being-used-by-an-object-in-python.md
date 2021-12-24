# 找出 Python 中一个对象正在使用多少内存

> 原文:[https://www . geesforgeks . org/find-了解 python 中的对象正在使用多少内存/](https://www.geeksforgeeks.org/find-out-how-much-memory-is-being-used-by-an-object-in-python/)

在本文中，我们将看到如何找出 Python 中的对象正在使用多少内存。为此，我们将使用 **sys.getsizeof()** 函数可以做到查找某个特定对象在内存中占据的存储空间大小。该函数返回对象的大小，单位为*字节*。它最多需要两个参数，即对象本身。

> **语法:** sys.getsizeof(object*)
> 
> **参数:** arg 可以是 int、str、function 等。
> 
> **返回:**给定对象的大小。

这个函数是通用的，可以处理任何数据类型，甚至一个函数。对于第一个系统，必须导入模块，然后将考虑中的对象传递给函数。下面给出了不同对象的不同实现。

**例 1:** 得到一个整数的大小。

## 蟒蛇 3

```
import sys

var = 1

print(sys.getsizeof(var))
```

**输出:**

```
28
```

**例 2:** 得到一个小数的大小。

## 蟒蛇 3

```
import sys

var = 1.2

print(sys.getsizeof(var))
```

**输出:**

```
24
```

**示例 3:** 获取一个字符串的大小。

## 蟒蛇 3

```
import sys

# string init
var1 = ""
var2 = "gfg"
var3 = "Welcome to gfg"

# get size of an object
print(sys.getsizeof(var1))
print(sys.getsizeof(var2))
print(sys.getsizeof(var3))
```

**输出:**

```
64
72
96
```

**示例 4:** 获取一个列表的大小。

## 蟒蛇 3

```
# import module
import sys

# list init
var1 = []
var2 = [1]
var3 = [1, 2, 3, 4]

# check size of obj
print(sys.getsizeof(var1))
print(sys.getsizeof(var2))
print(sys.getsizeof(var3))
```

**输出:**

```
64
72
96
```

**例 5:** 获取一个集合的大小。

## 蟒蛇 3

```
import sys

# set init
var1 = set([])
var2 = set([1, 2, 3, 4, 5])

# get size of object
print(sys.getsizeof(var1))
print(sys.getsizeof(var2))
```

**输出:**

```
224
736
```

**例 6:** 获取一个字典的大小。

## 蟒蛇 3

```
import sys

# dic
var1 = {'Apple':1}
var2 = {'Apple':1, 'ball': 2, 'cat':3, 
        'dog': 4, 'egg': 5, 'frog': 6}

# get the size of object
print(sys.getsizeof(var1))
print(sys.getsizeof(var2))
```

**输出:**

```
240
368
```

**例 7:** 得到一个函数的大小。

## 蟒蛇 3

```
import sys

def func():
    pass
var = func
print(sys.getsizeof(var))
```

**输出:**

```
136
```