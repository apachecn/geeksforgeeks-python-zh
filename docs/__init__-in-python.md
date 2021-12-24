# _ _ Python 中的 init _ _ _

> 原文:[https://www.geeksforgeeks.org/__init__-in-python/](https://www.geeksforgeeks.org/__init__-in-python/)

**先决条件–**[蟒蛇类](https://www.geeksforgeeks.org/python-classes-and-objects/)、[物体](https://www.geeksforgeeks.org/python-classes-and-objects/)、[自身](https://www.geeksforgeeks.org/self-in-python-class/)

每当用 Python 进行面向对象编程时，我们大多会遇到通常不太理解的`__init__` 方法。本文解释了`__init__` 的主要概念，但是在理解`__init__`之前需要一些先决条件。

## __init__

`__init__` 方法类似于`C++``Java`中的**构造函数**。构造函数用于初始化对象的状态。构造函数的任务是在创建类的对象时初始化(赋值)类的数据成员。与方法一样，构造函数也包含在对象创建时执行的语句(即指令)的集合。一旦类的对象被实例化，它就会运行。该方法对于您想要对对象进行的任何初始化都很有用。

**例:**

```
# A Sample class with init method  
class Person:  

    # init method or constructor   
    def __init__(self, name):  
        self.name = name  

    # Sample Method   
    def say_hi(self):  
        print('Hello, my name is', self.name)  

p = Person('Nikhil')  
p.say_hi()  
```

**输出:**

```
Hello, my name is Nikhil

```

#### 理解代码

在上面的示例中，创建了一个人名 Nikhil。在创建人的时候，“Nikhil”作为参数传递，这个参数会传递给`__init__` 方法初始化对象。关键字`self` 代表一个类的实例，并用给定的参数绑定属性。类似地，Person 类的许多对象可以通过传递不同的名称作为参数来创建。

**例:**

```
# A Sample class with init method  
class Person:  

    # init method or constructor   
    def __init__(self, name):  
        self.name = name  

    # Sample Method   
    def say_hi(self):  
        print('Hello, my name is', self.name)  

# Creating different objects     
p1 = Person('Nikhil')  
p2 = Person('Abhinav')
p3 = Person('Anshul')

p1.say_hi()  
p2.say_hi()
p3.say_hi()
```

**输出:**

```
Hello, my name is Nikhil
Hello, my name is Abhinav
Hello, my name is Anshul

```

#### __init__ 带继承

[继承](https://www.geeksforgeeks.org/inheritance-in-python/)是一个类从另一个类派生或继承属性的能力。让我们考虑下面的例子，看看 __init__ 是如何在继承中工作的。

```
# Python program to
# demonstrate init with
# inheritance

class A(object):
    def __init__(self, something):
        print("A init called")
        self.something = something

class B(A):
    def __init__(self, something):
        # Calling init of parent class
        A.__init__(self, something)
        print("B init called")
        self.something = something

obj = B("Something")
```

**输出:**

```
A init called
B init called

```

因此，首先调用父类构造函数。但是在 Python 中，并不强制总是首先调用父类构造函数。可以修改为父类或子类调用 __init__ 方法的顺序。这可以简单地通过在子类构造函数的主体之后调用父类构造函数来实现。

**例:**

```
# Python program to
# demonstrate init with
# inheritance

class A(object):
    def __init__(self, something):
        print("A init called")
        self.something = something

class B(A):
    def __init__(self, something):
        print("B init called")
        self.something = something
        # Calling init of parent class
        A.__init__(self, something)

obj = B("Something")
```

**输出:**

```
B init called
A init called

```

**注:**了解更多传承[点击此处](https://www.geeksforgeeks.org/inheritance-in-python/)。