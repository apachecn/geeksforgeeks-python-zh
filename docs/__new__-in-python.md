# _ _ Python 中的 new _ _ _

> 原文:[https://www.geeksforgeeks.org/__new__-in-python/](https://www.geeksforgeeks.org/__new__-in-python/)

[Python](https://www.geeksforgeeks.org/python-programming-language/) 是一种面向对象的编程语言，也就是说，Python 中的一切都是对象。Python 中有一种特殊的方法被称为[魔法方法](https://www.geeksforgeeks.org/dunder-magic-methods-python/)或 [dunder 方法](https://www.geeksforgeeks.org/dunder-magic-methods-python/) (dunder 在这里的意思是“*双下划线*”)。Python 中的 Dunder 或 magic 方法是在方法名中有两个前缀和后缀下划线的方法。这些通常用于运算符重载。
魔法的例子很少:`__init__`、`__add__`、`__len__`、`__repr__` 等。

**注意:**想了解更多魔法方法[点击这里](https://www.geeksforgeeks.org/dunder-magic-methods-python/)。

<center>

#### __ 新 _ _ 方法

每当一个类被实例化时`__new__` 和`__init__` 方法被调用。创建对象时将调用`__new__` 方法，并调用`__init__` 方法初始化对象。在基类`object`中，__new__ 方法被定义为需要传递参数`cls`的静态方法。`cls` 表示需要实例化的类，编译器在实例化时自动提供这个参数。

**语法:**

```
class class_name:
    def __new__(cls, *args, **kwargs):
        statements
        .
        .
        return super(class_name, cls).__new__(cls, *args, **kwargs)

```

**注意:**实例可以在`__new__` 方法内部通过使用`super` 函数或者直接在对象上调用`__new__` 方法来创建，其中如果父类是对象。那就是`instance = super(MyClass, cls).__new__(cls, *args, **kwargs)`或者`instance = object.__new__(cls, *args, **kwargs)`

如果 __init__ 方法和 __new__ 方法都存在于类中，那么 __new__ 方法将首先执行，并决定是否使用 __init__ 方法，因为 __new__ 方法可以调用其他类构造函数，或者它可以简单地返回其他对象作为该类的实例。

**示例:**

```
# Python program to 
# demonstrate __new__

# don't forget the object specified as base
class A(object):
    def __new__(cls):
         print("Creating instance")
         return super(A, cls).__new__(cls)

    def __init__(self):
        print("Init is called")

A()
```

**输出:**

```
Creating instance
Init is called

```

上面的例子显示了 __new__ 方法是在调用类名时自动调用的，而 __init__ 方法是在 __new__ 方法每次返回该类的一个实例时调用的，将返回的实例作为`self`参数传递给 __init__，因此，即使您要将该实例全局/静态地保存在某个地方，并在每次从 __new__ 返回它时，每次都将调用 __init__ 方法。

这意味着如果 __new__ 方法省略了 super，则 __init__ 方法将不会被执行。让我们看看情况是否如此。

```
# Python program to
# demonstrate __new__

class A(object):
    def __new__(cls):
        print("Creating instance")

    # It is not called
    def __init__(self):
        print("Init is called")

print(A())
```

**输出:**

```
Creating instance
None

```

在上面的例子中，可以看到 **__init__** 方法没有被调用，实例化被评估为`None` ，因为构造函数没有返回任何东西。让我们看看如果 __new__ 和 __init__ 方法都返回一些东西会发生什么。

```
# Python program to
# demonstrate __new__

class A(object):
    # new method returning a string
    def __new__(cls):
        print("Creating instance")
        return "GeeksforGeeks"

class B(object):
    # init method returning a string
    def __init__(self):
        print("Initializing instance")
        return "GeeksforGeeks"

print(A())
print(B())
```

**输出:**

```
Creating instance
GeeksforGeeks
Initializing instance

```

```
Traceback (most recent call last):
  File "/home/62216eb30d3856048eff916fb8d4c32d.py", line 17, in print(B())
TypeError: __init__() should return None, not 'str' 
```

这个类型错误是由调用 __init__ 方法的处理程序引发的，从 __init__ 方法返回任何东西都没有意义，因为它的目的只是改变新创建的实例的新状态。

让我们尝试一个例子，其中 __new__ 方法返回一个不同类的实例。
**例:**

```
# Python program to
# demonstrate __new__ method

# class whose object
# is returned
class GeeksforGeeks(object):
    def __str__(self):
        return "GeeksforGeeks"

# class returning object
# of different class
class Geek(object):
    def __new__(cls):
        return GeeksforGeeks()

    def __init__(self):
        print("Inside init")

print(Geek())
```

**输出:**

```
GeeksforGeeks

```

</center>