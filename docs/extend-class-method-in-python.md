# Python 中的扩展类方法

> 原文:[https://www . geesforgeks . org/extend-class-method-in-python/](https://www.geeksforgeeks.org/extend-class-method-in-python/)

在 Python 中，当一个子类定义一个已经存在于其超类中的函数，以便以自己的方式添加一些其他功能时，子类中的函数被称为扩展方法，这种机制被称为扩展。这是 Python 展示[多态性](https://www.geeksforgeeks.org/polymorphism-in-python/)的一种方式。这类似于在 Java 中重写和在 C++中重写虚拟方法。来自子类实例的调用执行子类版本的函数。调用超类的版本`super()`方法。

**为什么要扩展函数？**
通过[继承](https://www.geeksforgeeks.org/inheritance-in-python/)可以达到在 Python 中扩展类方法的目的。扩展方法的一个主要优点是它使代码可重用。此外，多个子类可以共享相同的代码，甚至可以根据需要更新代码。

我们将在这里处理这两种情况

**案例 1:没有扩展类方法**

```
# definition of superclass "Triangles"
class Triangles(object):

    count = 0

    # Calling Constructor
    def __init__(self, name, s1, s2, s3):
        self.name = name
        self.s1 = s1
        self.s2 = s2
        self.s3 = s3
        Triangles.count+= 1

    def setName(self, name):
        self.name = name

    def setdim(self, s1, s2, s3):
        self.s1 = s1
        self.s2 = s2
        self.s3 = s3

    def getcount(self):
        return Triangles.count

    def __str__(self):
        return 'Name: '+self.name+'\nDimensions: '+str(self.s1)+','+str(self.s2)+','+str(self.s3)

# describing a subclass 
# inherits from Triangles
class Peri(Triangles):

    # function to calculate the area     
    def calculate(self):
        self.pm = 0
        self.pm = self.s1 + self.s2 + self.s3

    # function to display just the area 
    # because it is not extended
    def display(self):
        return self.pm

def main():

    # instance of the subclass
    p = Peri('PQR', 2, 3, 4)
    # call to calculate()
    p.calculate()
    # explicit call to __str__()
    print(p.__str__())
    # call to display()
    print(p.display())

main()
```

**输出:**

```
Name: PQR
Dimensions: 2, 3, 4
9

```

**案例 2:扩展类方法**

```
# definition of superclass "Triangles"
class Triangles(object):

    count = 0

    def __init__(self, name, s1, s2, s3):
        self.name = name
        self.s1 = s1
        self.s2 = s2
        self.s3 = s3
        Triangles.count+= 1

    def setName(self, name):
        self.name = name

    def setdim(self, s1, s2, s3):
        self.s1 = s1
        self.s2 = s2
        self.s3 = s3

    def getcount(self):
        return Triangles.count

    # superclass's version of display()
    def display(self):
        return 'Name: '+self.name+'\nDimensions: '+str(self.s1)+', '+str(self.s2)+', '+str(self.s3)

# definition of the subclass
# inherits from "Triangles"
class Peri(Triangles):

    def calculate(self):
        self.pm = 0
        self.pm = self.s1 + self.s2 + self.s3

    # extended method 
    def display(self):

        # calls display() of superclass 
        print (super(Peri, self).display())

        # adding its own properties 
        return self.pm

def main():

    # instance of the subclass
    p = Peri('PQR', 2, 3, 4)

    # call to calculate
    p.calculate()

    # one call is enough 
    print(p.display())

main()
```

**输出:**

```
Name: PQR
Dimensions: 2, 3, 4
9

```

两种情况下产生的输出是相同的，唯一的区别是第二种情况使其他子类更容易继承这些方法，并根据需要“扩展”它们，如前所述，这增加了代码的可重用性。