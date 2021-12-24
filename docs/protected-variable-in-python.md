# Python 中的受保护变量

> 原文:[https://www.geeksforgeeks.org/protected-variable-in-python/](https://www.geeksforgeeks.org/protected-variable-in-python/)

**先决条件:**Python 中的[下划线(_)](https://www.geeksforgeeks.org/underscore-_-python/)

变量是我们分配给存储单元的标识符，存储单元用于保存计算机程序中的值。变量是程序中命名的存储位置。基于访问规范，变量在类中可以是公共的、受保护的和私有的。

**受保护变量**是一个类的数据成员，可以在该类和从该类派生的类中访问。在 Python 中，不存在“公共”实例变量。但是，我们使用**下划线“_”**符号来确定类中数据成员的访问控制。任何以下划线为前缀的成员都应该被视为应用编程接口或任何 Python 代码的非公共部分，无论它是函数、方法还是数据成员。

**例 1:**

```py
# program to illustrate protected
# data members in a class 

# Defining a class
class Geek: 

    # protected data members 
    _name = "R2J"
    _roll = 1706256

    # public member function 
    def displayNameAndRoll(self): 

        # accessing protected data members 
        print("Name: ", self._name) 
        print("Roll: ", self._roll) 

# creating objects of the class         
obj = Geek() 

# calling public member 
# functions of the class 
obj.displayNameAndRoll() 
```

**输出:**

```py
Name:  R2J
Roll:  1706256

```

**例 2:** 继承期间

```py
# program to illustrate protected
# data members in a class 

# super class 
class Shape: 

    # constructor 
    def __init__(self, length, breadth): 
        self._length = length
        self._breadth = breadth 

    # public member function 
    def displaySides(self): 

        # accessing protected data members 
        print("Length: ", self._length) 
        print("Breadth: ", self._breadth) 

# derived class 
class Rectangle(Shape): 

    # constructor 
    def __init__(self, length, breadth): 

        # Calling the constructor of
        # Super class
        Shape.__init__(self, length, breadth) 

    # public member function 
    def calculateArea(self): 

        # accessing protected data members of super class 
        print("Area: ", self._length * self._breadth) 

# creating objects of the 
# derived class         
obj = Rectangle(80, 50) 

# calling derived member 
# functions of the class
obj.displaySides()

# calling public member
# functions of the class 
obj.calculateArea() 
```

**输出:**

```py
Length:  80
Breadth:  50
Area:  4000

```

在上面的例子中，超级类`Shape`的保护变量`_length`和`_breadth`是通过成员函数`displaySides()`在类内访问的，并且可以从类`Rectangle`访问，该类是从`Shape`类派生的。类`Rectangle`的成员函数`calculateArea()`访问超类`Shape`的受保护数据成员`_length`和`_breadth`，计算矩形的面积。