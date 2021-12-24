# Python 中的 dir()函数

> 原文:[https://www.geeksforgeeks.org/python-dir-function/](https://www.geeksforgeeks.org/python-dir-function/)

***【dir()】*****是 Python3 中一个强大的内置函数，它返回任何对象(比如函数、模块、字符串、列表、字典等)的属性和方法列表。)
**语法:**** 

```
dir({object})
```

****参数:**** 

```
**object** *[optional]* : Takes object name
```

> ****返回:**
> dir()试图返回调用它的对象的有效属性列表。此外，dir()函数对于不同类型的对象表现得相当不同，因为它旨在生成最相关的对象，而不是完整的信息。** 
> 
> *   **对于类对象，它还返回所有有效属性和基本属性的名称列表。** 
> *   **对于模块/库对象，它试图返回包含在该模块中的所有属性的名称列表。** 
> *   **如果没有传递参数，它将返回当前本地范围内的名称列表。**

 ****代码#1 :** 有无导入外部库。** 

## **蟒蛇 3**

```
# Python3 code to demonstrate dir()
# when no parameters are passed

# Note that we have not imported any modules
print(dir())

# Now let's import two modules
import random
import math

# return the module names added to
# the local namespace including all
# the existing ones as before
print(dir())
```

****输出:**** 

```
['__builtins__', '__cached__', '__doc__', '__file__', '__loader__',
                                          '__name__', '__package__', '__spec__']

['__builtins__', '__cached__', '__doc__', '__file__', '__loader__',
                         '__name__', '__package__', '__spec__', 'math', 'random']
```

 ****代码#2 :**** 

## **蟒蛇 3**

```
# Python3 code to demonstrate dir() function
# when a module Object is passed as parameter.

# import the random module
import random

# Prints list which contains names of
# attributes in random function
print("The contents of the random library are::")

# module Object is passed as parameter
print(dir(random))
```

****输出:**** 

```
The contents of the random library are ::

['BPF', 'LOG4', 'NV_MAGICCONST', 'RECIP_BPF', 'Random', 'SG_MAGICCONST',
'SystemRandom', 'TWOPI', '_BuiltinMethodType', '_MethodType', '_Sequence',
'_Set', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__',
'__name__', '__package__', '__spec__', '_acos', '_ceil', '_cos', '_e', '_exp',
'_inst', '_log', '_pi', '_random', '_sha512', '_sin', '_sqrt', '_test', '_test_generator',
'_urandom', '_warn', 'betavariate', 'choice', 'expovariate', 'gammavariate', 'gauss',
'getrandbits', 'getstate', 'lognormvariate', 'normalvariate', 'paretovariate', 'randint',
'random', 'randrange', 'sample', 'seed', 'setstate', 'shuffle', 'triangular', 'uniform',
'vonmisesvariate', 'weibullvariate']
```

 ****代码#3 :** 对象作为参数传递。** 

## **蟒蛇 3**

```
# When a list object is passed as
# parameters for the dir() function

# A list, which contains
# a few random values
geeks = ["geeksforgeeks", "gfg", "Computer Science",
                    "Data Structures", "Algorithms" ]

# dir() will also list out common
# attributes of the dictionary
d = {}   # empty dictionary

# dir() will return all the available
# list methods in current local scope
print(dir(geeks))

# Call dir() with the dictionary
# name "d" as parameter. Return all
# the available dict methods in the
# current local scope
print(dir(d))
```

****输出:**** 

```
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__',
'__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', 
'__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', 
'__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', 
'__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', 
'__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 
'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']

['__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', 
'__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', 
'__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__ne__', 
'__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__setitem__', 
'__sizeof__', '__str__', '__subclasshook__', 'clear', 'copy', 'fromkeys', 'get', 'items', 
'keys', 'pop', 'popitem', 'setdefault', 'update', 'values']
```

 ****代码#4 :** 用户定义–具有可用 __dir()__ 方法的类对象作为参数传递。** 

## **蟒蛇 3**

```
# Python3 program to demonstrate working
# of dir(), when user defined objects are
# passed are parameters.

# Creation of a simple class with __dir()__
# method to demonstrate it's working
class Supermarket:

    # Function __dir()___ which list all
    # the base attributes to be used.
    def __dir__(self):
        return['customer_name', 'product',
               'quantity', 'price', 'date']

# user-defined object of class supermarket
my_cart = Supermarket()

# listing out the dir() method
print(dir(my_cart))
```

****输出:**** 

```
['customer_name', 'date', 'price', 'product', 'quantity']
```

 ****应用:**** 

*   ****dir()** 有自己的一套用法。它通常用于简单的日常程序中的*调试目的*，甚至在开发团队承担的大型项目中。dir()列出传递的参数的所有属性的能力，在分别处理许多类和函数时非常有用。** 
*   ****dir()** 功能还可以列出模块/列表/字典的所有可用属性。因此，它还为我们提供了关于可用列表或模块可以执行的操作的信息，这在几乎没有关于模块的信息时非常有用。这也有助于更快地了解新模块。**