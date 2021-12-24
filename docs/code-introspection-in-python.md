# Python 中的代码自省

> 原文:[https://www.geeksforgeeks.org/code-introspection-in-python/](https://www.geeksforgeeks.org/code-introspection-in-python/)

内省是一种在运行时确定对象类型的能力。python 中的一切都是一个对象。Python 中的每个对象都可能有属性和方法。通过使用内省，我们可以动态地检查 python 对象。代码内省用于检查类、方法、对象、模块、关键字，并获取关于它们的信息，以便我们可以利用它。内省揭示了关于程序对象的有用信息。Python 作为一种动态的、面向对象的编程语言，提供了巨大的内省支持。Python 对内省的支持贯穿于语言的方方面面。
Python 提供了一些用于代码自省的内置函数。它们是:
1。 **type() :** 这个函数返回一个对象的类型。

```py
# Python program showing
# a use of type function

import math

# print type of math
print(type(math))

# print type of 1 
print(type(1))

# print type of "1"
print(type("1"))

# print type of rk
rk =[1, 2, 3, 4, 5, "radha"]

print(type(rk))
print(type(rk[1]))
print(type(rk[5]))
```

**输出:**

```py
<class 'module'>
<class 'int'>
<class 'str'>
<class 'list'>
<class 'int'>
<class 'str'>

```

2。 **dir() :** 这个函数返回与那个对象相关的方法和属性的列表。

```py
# Python program showing
# a use of dir() function

import math
rk =[1, 2, 3, 4, 5]

# print methods and attributes of rk
print(dir(rk))
rk =(1, 2, 3, 4, 5)

# print methods and attributes of rk
print(dir(rk))
rk ={1, 2, 3, 4, 5}

print(dir(rk))
print(dir(math))
```

**Output:**

```py
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'count', 'index']
['__doc__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'copysign', 'cos', 'cosh', 'degrees', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'pi', 'pow', 'radians', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'trunc']

```

3。 **str() :** 这个函数把所有的东西都转换成一个字符串。

```py
# Python program showing
# a use of str() function

a = 1
print(type(a))

# converting integer
# into string
a = str(a)
print(type(a))

s =[1, 2, 3, 4, 5]
print(type(s))

# converting list
# into string
s = str(s)
print(type(s))
```

**输出:**

```py
<class 'int'>
<class 'str'>
<class 'list'>
<class 'str'>

```

4。 **id() :** 这个函数返回一个对象的特殊 id。

```py
# Python program showing
# a use of id() function

import math
a =[1, 2, 3, 4, 5]

# print id of a
print(id(a))
b =(1, 2, 3, 4, 5)

# print id of b
print(id(b))
c ={1, 2, 3, 4, 5}

# print id of c
print(id(c))
print(id(math))
```

**输出:**

```py
139787756828232
139787757942656
139787757391432
139787756815768

```

#### 代码自省的方法

| 功能 | 描述 |
| **帮助()** | 它被用来查找其他函数的作用 |
| **hasattr()** | 检查对象是否有属性 |
| get attr() | 如果有属性，则返回属性的内容。 |
| 压抑() | 返回对象的字符串表示形式 |
| **可调用()** | 检查对象是否是可调用对象(函数)。 |
| **issubclass()** | 检查特定类是否是另一个类的派生类。 |
| **情况()** | 检查对象是否是特定类的实例。 |
| **缝合()** | 允许访问系统特定的变量和函数 |
| **__doc__** | 返回一些关于对象的文档 |
| **_ _ 名称 __** | 返回对象的名称。 |