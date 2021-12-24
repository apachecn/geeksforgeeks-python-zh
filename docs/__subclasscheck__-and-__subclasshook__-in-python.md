# _ _ Python 中的 subclasscheck__ 和 _ _ subclass hook _ _

> 原文:[https://www . geesforgeks . org/_ _ subclass check _ _-和 __subclasshook__-in-python/](https://www.geeksforgeeks.org/__subclasscheck__-and-__subclasshook__-in-python/)

[类](https://www.geeksforgeeks.org/python-classes-and-objects/)是数据(变量和方法)的集合。它将数据和功能捆绑在一起。它提供了面向对象编程的所有标准特性。基本上它是一个创建对象的蓝图。创建一个新类会创建一个新类型的对象，从而允许创建该类型的新实例。

**示例:**

```py
# class 'A' defined
class A(object):

    # Calling Constructor
    def __init__(self, a):

        self.a = a
        print("The value of a:", self.a)

# Driver's code
c = A(7)
```

**输出:**

```py
The value of a: 7

```

#### _ _ Python 中的子类 check__ 方法

`__subclasscheck__`是自定义`issubclass()`内置功能结果的方法之一。检查一个类是否是子类的方法，如果认为该类是另一个类的子类(直接或间接)，则返回`True`，否则返回`False`。它不能被定义为实际/真实类中的类方法。它是在元类中实现的，因为它不是为普通类实现的。为了更好地理解，考虑下面的例子。

**示例:**考虑一种情况，您想使用`issubclass()`方法检查某个值是否作为属性存在于类中。

```py
# Python program to demonstrate
# subclasscheck

class A(type):

    # __subclasscheck__() defined
    def __subclasscheck__(cls, sub):

        # Getting the L attribute of
        # subclass
        attr = getattr(cls, 'L', [])

        # Checking if the subclass
        # is present in the L attribute
        # of subclass or not
        if sub in attr:
            return True

        return False

class B(metaclass = A):

    # L Attribute
    L = [1, 2, 3, 4, 5]

class C(metaclass = A):

    # L Attribute
    L = ["Geeks", "For"]

# Driver's code
print(issubclass(1, B))
print(issubclass("Geeks", B))
print(issubclass("Geeks", C))
```

**输出:**

```py
True
False
True

```

#### Python 中的 __subclasshook__ 方法

抽象类可以覆盖`__subclasshook__()`方法自定义`issubclass()`。当发现一个类是 ABC 类的子类时，它返回`True`，如果不是，它返回`False`，如果子类检查以通常的机制继续，它返回“未实现”。这个方法是在 ABC 类中定义的，有一些条件。符合这些条件的类被认为是子类。

**注:**必须定义为类方法。

**示例:**

```py
# Python program to demonstrate
# subclasshook

from abc import ABCMeta

class A(metaclass = ABCMeta):

    @classmethod
    def __subclasshook__(cls, C):
        if cls is A:

            # condition to check if the 
            # function anyfun() is present 
            # in any sub class or not
            if any("__anyfun__" in Q.__dict__ 
                   for Q in C.__mro__): 
                return True

        return False

class P(object):
    pass

class Q(object):

    def __anyfun__(self):
        return 0

# Driver's code
print(issubclass(Q, A) ) 
print(issubclass(P, A)  )
```

**输出:**

```py
True
False

```