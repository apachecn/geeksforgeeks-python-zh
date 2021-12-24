# Python 中的抽象类

> 原文:[https://www.geeksforgeeks.org/abstract-classes-in-python/](https://www.geeksforgeeks.org/abstract-classes-in-python/)

一个抽象类可以被认为是其他类的蓝图。它允许您创建一组方法，这些方法必须在从抽象类构建的任何子类中创建。包含一个或多个抽象方法的类称为抽象类。抽象方法是有声明但没有实现的方法。当我们设计大型功能单元时，我们使用抽象类。当我们想要为一个组件的不同实现提供一个公共接口时，我们使用一个抽象类。

**为什么要使用抽象基类:**
通过定义抽象基类，可以为一组子类定义通用的应用程序接口(API)。这种能力在第三方将要提供实现的情况下特别有用，例如使用插件，但是在大型团队或大型代码库中工作时，这种能力也可以帮助您，因为在大型团队或大型代码库中，很难或不可能记住所有类。

**抽象基类如何工作:**
默认情况下，Python 不提供抽象类。Python 附带了一个模块，为定义抽象基类提供了基础，该模块的名称是抽象基类。 ***ABC*** 通过将基类的方法装饰为抽象，然后将具体类注册为抽象基类的实现来工作。当用关键字@abstractmethod 修饰时，方法变得抽象。例如–

**代码 1:**

## 蟒蛇 3

```py
# Python program showing
# abstract base class work

from abc import ABC, abstractmethod

class Polygon(ABC):

    @abstractmethod
    def noofsides(self):
        pass

class Triangle(Polygon):

    # overriding abstract method
    def noofsides(self):
        print("I have 3 sides")

class Pentagon(Polygon):

    # overriding abstract method
    def noofsides(self):
        print("I have 5 sides")

class Hexagon(Polygon):

    # overriding abstract method
    def noofsides(self):
        print("I have 6 sides")

class Quadrilateral(Polygon):

    # overriding abstract method
    def noofsides(self):
        print("I have 4 sides")

# Driver code
R = Triangle()
R.noofsides()

K = Quadrilateral()
K.noofsides()

R = Pentagon()
R.noofsides()

K = Hexagon()
K.noofsides()
```

**输出:**

```py
I have 3 sides
I have 4 sides
I have 5 sides
I have 6 sides
```

**代码 2:**

## 蟒蛇 3

```py
# Python program showing
# abstract base class work

from abc import ABC, abstractmethod
class Animal(ABC):

    def move(self):
        pass

class Human(Animal):

    def move(self):
        print("I can walk and run")

class Snake(Animal):

    def move(self):
        print("I can crawl")

class Dog(Animal):

    def move(self):
        print("I can bark")

class Lion(Animal):

    def move(self):
        print("I can roar")

# Driver code
R = Human()
R.move()

K = Snake()
K.move()

R = Dog()
R.move()

K = Lion()
K.move()
```

**输出:**

```py
I can walk and run
I can crawl
I can bark
I can roar
```

**通过子类化实现:**
通过直接从基类子类化，我们可以避免显式注册类的需要。在这种情况下，Python 类管理用于将*插件最小实现*识别为实现抽象插件库。

## 蟒蛇 3

```py
# Python program showing
# implementation of abstract
# class through subclassing

import abc

class parent:      
    def geeks(self):
        pass

class child(parent):
    def geeks(self):
        print("child class")

# Driver code
print( issubclass(child, parent))
print( isinstance(child(), parent))
```

**输出:**

```py
True
True
```

使用直接子类化的一个副作用是，可以通过向基类查询从它派生的已知类的列表来找到插件的所有实现。

**抽象基类中的具体方法:**
具体类只包含具体(普通)方法，而抽象类可能同时包含具体方法和抽象方法。具体类提供抽象方法的实现，抽象基类也可以通过 super()调用方法来提供实现。

让我们看一下使用 super()调用方法的示例:

## 蟒蛇 3

```py
# Python program invoking a
# method using super()

import abc
from abc import ABC, abstractmethod

class R(ABC):
    def rk(self):
        print("Abstract Base Class")

class K(R):
    def rk(self):
        super().rk()
        print("subclass ")

# Driver code
r = K()
r.rk()
```

**输出:**

```py
Abstract Base Class
subclass
```

在上面的程序中，我们可以使用 super()调用抽象类中的方法。

**抽象属性:**
抽象类除了方法之外还包括属性，可以通过用@abstractproperty 定义具体类来要求属性。

## 蟒蛇 3

```py
# Python program showing
# abstract properties

import abc
from abc import ABC, abstractmethod

class parent(ABC):
    @abc.abstractproperty
    def geeks(self):
        return "parent class"
class child(parent):

    @property
    def geeks(self):
        return "child class"

try:
    r =parent()
    print( r.geeks)
except Exception as err:
    print (err)

r = child()
print (r.geeks)
```

**输出:**

```py
Can't instantiate abstract class parent with abstract methods geeks
child class
```

在上面的示例中，基类不能被实例化，因为它只有属性 getter 方法的抽象版本。

**抽象类实例化:**
抽象类是不完整的，因为它们有没有人的方法。如果 python 允许为抽象类创建一个对象，那么如果有人调用抽象方法，但没有实际的实现可以调用，就可以使用该对象。因此，我们使用一个抽象类作为模板，根据需要，我们在使用它之前对它进行扩展和构建。由于抽象类不是具体类，所以不能实例化。当我们为抽象类创建一个对象时，它会引发一个*错误*。

## 蟒蛇 3

```py
# Python program showing
# abstract class cannot
# be an instantiation
from abc import ABC,abstractmethod

class Animal(ABC):
    @abstractmethod
    def move(self):
        pass
class Human(Animal):
    def move(self):
        print("I can walk and run")

class Snake(Animal):
    def move(self):
        print("I can crawl")

class Dog(Animal):
    def move(self):
        print("I can bark")

class Lion(Animal):
    def move(self):
        print("I can roar")

c=Animal()
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/ffe4267d930f204512b7f501bb1bc489.py", line 19, in 
    c=Animal()
TypeError: Can't instantiate abstract class Animal with abstract methods move
```