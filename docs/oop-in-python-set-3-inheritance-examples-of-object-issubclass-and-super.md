# Python 中的 OOP |集合 3(继承，对象、issubclass 和 super 的例子)

> 原文:[https://www . geesforgeks . org/OOP-in-python-set-3-继承-对象示例-issubclass-and-super/](https://www.geeksforgeeks.org/oop-in-python-set-3-inheritance-examples-of-object-issubclass-and-super/)

我们已经讨论了以下关于 Python 面向对象编程的主题

*   [Python 中的面向对象编程| set-1](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-1-class-and-its-members/)
*   [Python 中的面向对象编程|集合 2(数据隐藏和对象打印)](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-2-data-hiding-and-object-printing/ "Permalink to Object Oriented Programming in Python | Set 2 (Data Hiding and Object Printing)")

本文介绍了继承。

面向对象编程的主要优势之一是重用。继承是实现相同的机制之一。在继承中，一个类(通常称为超类)被另一个类(通常称为子类)继承。子类给超类增加了一些属性。

下面是一个示例 Python 程序，展示了如何在 Python 中实现继承。

```py

# A Python program to demonstrate inheritance 

# Base or Super class. Note object in bracket.
# (Generally, object is made ancestor of all classes)
# In Python 3.x "class Person" is 
# equivalent to "class Person(object)"
class Person(object):

    # Constructor
    def __init__(self, name):
        self.name = name

    # To get name
    def getName(self):
        return self.name

    # To check if this person is employee
    def isEmployee(self):
        return False

# Inherited or Sub class (Note Person in bracket)
class Employee(Person):

    # Here we return true
    def isEmployee(self):
        return True

# Driver code
emp = Person("Geek1")  # An Object of Person
print(emp.getName(), emp.isEmployee())

emp = Employee("Geek2") # An Object of Employee
print(emp.getName(), emp.isEmployee())
```

**Output:**

```py
('Geek1', False)
('Geek2', True)

```

**如何检查一个类是否是另一个类的子类？**
Python 提供了一个函数 issubclass()，直接告诉我们一个类是否是另一个类的子类。

```py
# Python example to check if a class is
# subclass of another

class Base(object):
    pass   # Empty Class

class Derived(Base):
    pass   # Empty Class

# Driver Code
print(issubclass(Derived, Base))
print(issubclass(Base, Derived))

d = Derived()
b = Base()

# b is not an instance of Derived
print(isinstance(b, Derived))

# But d is an instance of Base
print(isinstance(d, Base))
```

**Output:**

```py
True
False
False
True

```

**什么是对象类？**
和 Java Object 类一样，在 Python 中(来自 3.x 版本)，Object 是所有类的根。

在 Python 3.x 中，“类测试(对象)”和“类测试”是相同的。
在 Python 2.x 中，“类 Test(object)”创建以对象为父类的类(称为新样式类)，“类 Test”创建旧样式类(没有对象父类)。更多详情请参考[本](https://docs.python.org/release/2.2.3/whatsnew/sect-rellinks.html)。

**Python 支持多重继承吗？**
与 Java 不同，与 C++一样，Python 支持多重继承。我们将所有父类指定为括号中的逗号分隔列表。

```py
# Python example to show working of multiple 
# inheritance
class Base1(object):
    def __init__(self):
        self.str1 = "Geek1"
        print "Base1"

class Base2(object):
    def __init__(self):
        self.str2 = "Geek2"        
        print "Base2"

class Derived(Base1, Base2):
    def __init__(self):

        # Calling constructors of Base1
        # and Base2 classes
        Base1.__init__(self)
        Base2.__init__(self)
        print "Derived"

    def printStrs(self):
        print(self.str1, self.str2)

ob = Derived()
ob.printStrs()
```

**Output:**

```py
Base1
Base2
Derived
('Geek1', 'Geek2')

```

**如何访问子类中的父成员？**

1.  **使用父类名**

    ```py
    # Python example to show that base
    # class members can be accessed in
    # derived class using base class name
    class Base(object):

        # Constructor
        def __init__(self, x):
            self.x = x    

    class Derived(Base):

        # Constructor
        def __init__(self, x, y):
            Base.x = x 
            self.y = y

        def printXY(self):

           # print(self.x, self.y) will also work
           print(Base.x, self.y)

    # Driver Code
    d = Derived(10, 20)
    d.printXY()
    ```

    **输出:**

    ```py
    (10, 20)

    ```

2.  **Using super()**
    We can also access parent class members using super.

    ```py
    # Python example to show that base
    # class members can be accessed in
    # derived class using super()
    class Base(object):

        # Constructor
        def __init__(self, x):
            self.x = x    

    class Derived(Base):

        # Constructor
        def __init__(self, x, y):

            ''' In Python 3.x, "super().__init__(name)"
                also works''' 
            super(Derived, self).__init__(x)
            self.y = y

        def printXY(self):

           # Note that Base.x won't work here
           # because super() is used in constructor
           print(self.x, self.y)

    # Driver Code
    d = Derived(10, 20)
    d.printXY()
    ```

    **Output:**

    ```py
    (10, 20)

    ```

    请注意，上述两种方法并不完全相同。在下一篇关于继承的文章中，我们将涉及以下主题。
    1)超级如何工作？通过超级和父类名访问成员有何不同？
    2)Python 如何处理钻石问题？

    **练习:**
    预测以下 Python 程序的输出

    1.  ```py

        class X(object):
            def __init__(self, a):
                self.num = a
            def doubleup(self):
                self.num *= 2

        class Y(X):
            def __init__(self, a):
                X.__init__(self, a)
            def tripleup(self):
                self.num *= 3

        obj = Y(4)
        print(obj.num)

        obj.doubleup()
        print(obj.num)

        obj.tripleup()
        print(obj.num)
        ```

        **输出:**

        ```py
        4
        8
        24

        ```

    2.  ```py
        # Base or Super class
        class Person(object):
            def __init__(self, name):
                self.name = name

            def getName(self):
                return self.name

            def isEmployee(self):
                return False

        # Inherited or Subclass (Note Person in bracket)
        class Employee(Person):
            def __init__(self, name, eid):

                ''' In Python 3.0+, "super().__init__(name)"
                    also works''' 
                super(Employee, self).__init__(name)
                self.empID = eid

            def isEmployee(self):
                return True

            def getID(self):
                return self.empID

        # Driver code
        emp = Employee("Geek1", "E101") 
        print(emp.getName(), emp.isEmployee(), emp.getID())
        ```

        **输出:**

        ```py
        ('Geek1', True, 'E101')

        ```

    本文由**Shwetanshu Rohatgi****Mayank Rawat**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论