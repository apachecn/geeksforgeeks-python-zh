# Python 内部类中的继承

> 原文:[https://www . geeksforgeeks . org/python 中的继承-内部类/](https://www.geeksforgeeks.org/inheritance-in-python-inner-class/)

类是用户定义的蓝图或原型，从中创建对象。类提供了一种将数据和功能捆绑在一起的方法。创建一个新类会创建一个新类型的对象，从而允许创建该类型的新实例。每个类实例都可以附加属性来维护其状态。类实例也可以有方法(由其类定义)来修改其状态。

内部类或嵌套类是在另一个类的主体中定义的。如果使用类创建对象，则可以使用根类中的对象。一个类可以有一个或多个内部类。内部类或嵌套类在许多方面帮助用户，例如类的逻辑分组、更易读和更容易维护等。

例如，考虑一个类 DOB 在另一个类 Person 中的情况，并查看下面的代码片段。

```
class person:
    def __init__(self):
        self.name = 'AKASH'
        self.db = self.Dob()   #this is Dob object

```

在前面的代码中，“数据库”表示内部类对象。创建外部类对象时，它包含一个作为内部类对象的子对象。因此，我们可以将外部类和内部类成员称为:

```
p = person()  #create outer class object
p.display()   #call outer class method

x = p.db     #create inner class object
x.display()    #call inner class method

```

**例:**

```
# Python program to demonstrate
# inner class

class person:
    def __init__(self):
        self.name = 'AKASH'
        self.db = self.Dob()

    def display(self):
        print('NAME = ', self.name)

    # this is inner class
    class Dob:
        def __init__(self):
            self.dd = 10
            self.mm = 3
            self.yy = 2000
        def display(self):
            print('DOB = {}/{}/{}'.format(self.dd, self.mm, self.yy))

# creating person class object
p = person()
p.display()

# create inner class object
x = p.db
x.display()
```

**输出:**

```
NAME =  AKASH
DOB = 10/3/2000

```

#### 内部类中的继承

继承是一个类从另一个类中派生或继承属性的能力。继承的好处是:

*   It well represents the relationship in the real world.
*   It provides code reusability. We don't have to write the same code again and again. In addition, it allows us to add more features to the class without modifying the class.
*   It is transitive in nature, that is, if Class B inherits from another Class A, all subclasses of B will automatically inherit from Class A.

要在内部类中使用继承，请考虑下面的代码片段。

```
# Python program to demonstrate
# inheritance in inner class

class A:
    def __init__(self):
        self.db = self.Inner()

    def display(self):
        print('In Parent Class')

    # this is inner class
    class Inner:

        def display1(self):
            print('Inner Of Parent Class')

class B(A):
    def __init__(self):
        print('In Child Class')
        super().__init__()

    class Inner(A.Inner):

        def display2(self):
            print('Inner Of Child Class')

# creating child class object
p = B()
p.display()

# create inner class object
x = p.db
x.display1()
x.display2()
```

**输出:**

```
In Child Class
In Parent Class
Inner Of Parent Class
Inner Of Child Class

```

在上例中，B 类从 A 继承，B 的内部类从 A 的内部类继承，然后从孩子的内部类对象调用 Parent 的 inner 类的类方法。