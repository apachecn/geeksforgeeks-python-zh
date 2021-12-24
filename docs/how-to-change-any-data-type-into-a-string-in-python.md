# 如何在 Python 中将任意数据类型变成字符串？

> 原文:[https://www . geeksforgeeks . org/如何将任何数据类型更改为 python 字符串/](https://www.geeksforgeeks.org/how-to-change-any-data-type-into-a-string-in-python/)

Python 定义了类型转换函数，直接将一种数据类型转换成另一种数据类型，这在日常和竞争性编程中非常有用。字符串是一系列字符。字符串是 Python 中最流行的类型之一。我们可以通过在引号中包含字符来创建它们。

**示例:**以不同方式创建字符串:

```py
# creating string using ' '
str1 = 'Welcome to the Geeks for Geeks !'
print(str1)

# creating string using " "
str2 = "Welcome Geek !"
print(str2)

# creating string using ''' '''
str3 = '''Welcome again'''
print(str3)
```

**输出:**

```py
Welcome to the Geeks for Geeks!
Welcome Geek!
Welcome again
```

## 将任何数据类型更改为字符串

在 Python 中，有两种方法可以将任何数据类型更改为字符串:

1.  使用`str()`功能
2.  使用`__str__()`功能

**方法 1 :** 使用 `str()`函数
任何内置数据类型都可以通过`str()`函数转换为其字符串表示。python 内置的数据类型包括:- `int`、`float`、`complex`、`list`、`tuple`、`dict` 等。
**语法:**

```py
str(built-in data type)
```

**示例:**

```py
# a is of type int
a = 10
print("Type before : ", type(a))

# converting the type from int to str
a1 = str(a)
print("Type after : ", type(a1))

# b is of type float
b = 10.10
print("\nType before : ", type(b))

# converting the type from float to str
b1 = str(b)
print("Type after : ", type(b1))

# type of c is list
c = [1, 2, 3]
print("\nType before :", type(c))

# converting the type from list to str
c1 = str(c)
print("Type after : ", type(c1))

# type of d is tuple
d = (1, 2, 3)
print("\nType before:-", type(d))

# converting the type from tuple to str
d1 = str(d)
print("Type after:-", type(d1))
```

**输出:**

```py
Type before : <class 'int'>
Type after : <class 'str'>

Type before : <class 'float'>
Type after : <class 'str'>

Type before : <class 'list'>
Type after : <class 'str'>

Type before : <class 'tuple'>
Type after : <class 'str'>

```

**方法 2 :** 为要转换为字符串表示的用户定义类定义`__str__()`函数。对于要转换为字符串表示的用户定义类，需要在其中定义`__str__()`函数。

**示例:**

```py
# class addition
class addition:
    def __init__(self):
        self.a = 10
        self.b = 10

    # defining __str__() function
    def __str__(self):
        return 'value of a = {} value of b = {}'.format(self.a, self.b)

# creating object ad
ad = addition()
print(str(ad))

# printing the type
print(type(str(ad)))
```

**输出:**

```py
value of a =10 value of b =10
<class 'str'>
```