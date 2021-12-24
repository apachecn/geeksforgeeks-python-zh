# Python 中的私有方法

> 原文:[https://www.geeksforgeeks.org/private-methods-in-python/](https://www.geeksforgeeks.org/private-methods-in-python/)

**先决条件–**

*   [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)
*   [封装](https://www.geeksforgeeks.org/encapsulation-in-python/)
*   [Python 中的下划线](https://www.geeksforgeeks.org/underscore-_-python/)

封装是面向对象编程的基本概念之一。它描述了包装数据的思想以及在一个单元中处理数据的方法。这就对直接访问变量和方法设置了限制，可以防止数据的意外修改。类是封装的一个例子，因为它封装了成员函数、变量等所有数据。

现在，可能会有一些场景，我们需要对类的一些方法进行限制，这样它们既不能被类外访问，也不能被任何子类访问。为了实现这一点，私有方法开始发挥作用。

## 私有方法

考虑一个现实生活中的例子，汽车发动机，它由许多零件组成，如火花塞、阀门、活塞等。没有用户直接使用这些部件，相反，他们只知道如何使用使用它们的部件。这就是私有方法的用途。它用于向外界隐藏任何类的内部功能。

私有方法是那些既不应该被类外访问也不应该被任何基类访问的方法。在 Python 中，不存在不能被访问的私有方法，除非在类中。但是，要定义私有方法，请在成员名称前加双下划线“”**_ _**”。

**注意:** `__init__` 方法是一个构造函数，只要一个类的对象被实例化就运行。

```
# Python program to 
# demonstrate private methods

# Creating a Base class 
class Base: 

    # Declaring public method
    def fun(self):
        print("Public method")

    # Declaring private method
    def __fun(self):
        print("Private method")

# Creating a derived class 
class Derived(Base): 
    def __init__(self): 

        # Calling constructor of 
        # Base class 
        Base.__init__(self) 

    def call_public(self):

        # Calling public method of base class
        print("\nInside derived class")
        self.fun()

    def call_private(self):

        # Calling private method of base class
        self.__fun()

# Driver code 
obj1 = Base()

# Calling public method
obj1.fun()

obj2 = Derived()
obj2.call_public()

# Uncommenting obj1.__fun() will 
# raise an AttributeError 

# Uncommenting obj2.call_private() 
# will also raise an AttributeError
```

**输出:**

```
Public method

Inside derived class
Public method

```

```
Traceback (most recent call last):
  File "/home/09d6f91fdb63d16200e172c7a925dd7f.py", line 43, in obj1.__fun() 
AttributeError: 'Base' object has no attribute '__fun'

Traceback (most recent call last):
  File "/home/0d5506bab8f06cb7c842501d9704557b.py", line 46, in <module>obj2.call_private() 
  File "/home/0d5506bab8f06cb7c842501d9704557b.py", line 32, in call_private
    self.__fun()
AttributeError: 'Derived' object has no attribute '_Derived__fun'</module> 
```

上面的例子显示了类的私有方法既不能被类外访问，也不能被任何基类访问。但是，可以通过公共方法调用私有方法来访问私有方法。

**示例:**

```
# Python program to 
# demonstrate private methods

# Creating a class 
class A: 

    # Declaring public method
    def fun(self):
        print("Public method")

    # Declaring private method
    def __fun(self):
        print("Private method")

    # Calling private method via
    # another method
    def Help(self):
        self.fun()
        self.__fun()

# Driver's code
obj = A()
obj.Help()
```

**输出:**

```
Public method
Private method

```

#### 名字叫芒灵

Python 提供了一个魔杖，可以用来调用类外的私有方法，也就是所谓的 mangling。这意味着任何形式为 __geek 的标识符(至少两个前导下划线或最多一个尾随下划线)都被替换为 _ classname _ _ geek，其中 classname 是去掉前导下划线的当前类名。

**示例:**

```
# Python program to 
# demonstrate private methods

# Creating a class 
class A: 

    # Declaring public method
    def fun(self):
        print("Public method")

    # Declaring private method
    def __fun(self):
        print("Private method")

# Driver's code
obj = A()

# Calling the private member 
# through name mangling
obj._A__fun()
```

**输出:**

```
Private method

```