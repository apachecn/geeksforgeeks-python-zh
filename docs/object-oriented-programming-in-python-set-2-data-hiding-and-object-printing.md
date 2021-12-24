# Python 中的面向对象编程|集合 2(数据隐藏和对象打印)

> 原文:[https://www . geesforgeks . org/面向对象的 python 编程-set-2-数据隐藏和对象打印/](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-2-data-hiding-and-object-printing/)

前提条件:面向对象[Python 编程|集合 1(类、对象和成员)](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-1-class-and-its-members/)

**数据隐藏**

在 Python 中，我们在属性名称前使用双下划线(Or __)，这些属性在外部将不直接可见。

## 计算机编程语言

```py
class MyClass:

    # Hidden member of MyClass
    __hiddenVariable = 0

    # A member method that changes
    # __hiddenVariable
    def add(self, increment):
        self.__hiddenVariable += increment
        print (self.__hiddenVariable)

# Driver code
myObject = MyClass()    
myObject.add(2)
myObject.add(5)

# This line causes error
print (myObject.__hiddenVariable)
```

输出:

```py
2
7
Traceback (most recent call last):
  File "filename.py", line 13, in 
    print (myObject.__hiddenVariable)
AttributeError: MyClass instance has 
no attribute '__hiddenVariable' 
```

在上面的程序中，我们试图使用一个对象访问类外的一个隐藏变量，它抛出了一个异常。
我们可以通过一个复杂的语法来访问隐藏属性的值:

## 计算机编程语言

```py
# A Python program to demonstrate that hidden
# members can be accessed outside a class
class MyClass:

    # Hidden member of MyClass
    __hiddenVariable = 10

# Driver code
myObject = MyClass()    
print(myObject._MyClass__hiddenVariable)
```

输出:

```py
10
```

私有方法可以在类外访问，只是不容易访问。**Python 中没有什么是真正私有的；在内部**，私有方法和属性的名称会被动态打乱，使它们看起来无法通过给定的名称访问【参见[本文](http://pages.cs.wisc.edu/~zeyuan/projects/notes/diveintopython/chap5.html)获取来源】。

**打印对象**

打印对象为我们提供了关于正在处理的对象的信息。在 C++中，我们可以通过添加好友 ostream& operator << (ostream&, const Foobar&) method for the class. In Java, we use toString() method.
来实现，在 python 中，这可以通过使用 __repr__ 或 __str__ 方法来实现。

## 计算机编程语言

```py
class Test:
    def __init__(self, a, b):
        self.a = a
        self.b = b

    def __repr__(self):
        return "Test a:%s b:%s" % (self.a, self.b)

    def __str__(self):
        return "From str method of Test: a is %s," \
              "b is %s" % (self.a, self.b)

# Driver Code       
t = Test(1234, 5678)
print(t) # This calls __str__()
print([t]) # This calls __repr__()
```

输出:

```py
From str method of Test: a is 1234,b is 5678
[Test a:1234 b:5678]
```

**关于打印的要点:**

*   如果未定义 __str__ 方法，print t(或 print str(t))将使用 __repr__。

## 计算机编程语言

```py
class Test:
    def __init__(self, a, b):
        self.a = a
        self.b = b

    def __repr__(self):
        return "Test a:%s b:%s" % (self.a, self.b)

# Driver Code       
t = Test(1234, 5678)
print(t)
```

输出:

```py
Test a:1234 b:5678
```

*   如果没有定义 __repr__ 方法，则使用默认值。

## 计算机编程语言

```py
class Test:
    def __init__(self, a, b):
        self.a = a
        self.b = b

# Driver Code       
t = Test(1234, 5678)
print(t)
```

输出:

```py
<__main__.Test instance at 0x7fa079da6710> 
```

本文由 **Shwetanshu Rohatgi** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。