# Python 中的内部类

> 原文:[https://www.geeksforgeeks.org/inner-class-in-python/](https://www.geeksforgeeks.org/inner-class-in-python/)

A **Python** 是一种面向对象的编程语言，Python 中的一切都与对象、方法和属性有关。类是用户定义的蓝图或原型，我们可以用它来创建类的对象。该类是使用 class 关键字定义的。

**类示例–**

```py
# create a Geeksforgeeks class
class Geeksforgeeks :
   gfg = 10
```

首先我们要了解 [__init__()](https://www.geeksforgeeks.org/__init__-in-python/) 内置的理解类含义的方法。每当类被启动时，总是会执行一个方法，即 __init__()方法。__init__()方法用于将值分配给对象属性，或者执行创建对象时需要完成的其他方法。

**带有 __init__()方法的类示例–**

```py
# create a Geeksforgeeks class
class Geeksforgeeks:

 # constructor method
 def __init__(self):

  # object attributes
  self.course = "Campus preparation"
  self.duration = "2 months"

 # define a show method
 # for printing the content
 def show(self):
  print("Course:", self.course)
  print("Duration:", self.duration)

# create Geeksforgeeks 
# class object
outer = Geeksforgeeks()

# method calling
outer.show()
```

**输出:**

```py
 Course : Campus Preparation
Duration : As per your schedule 
```

## Python 中的内部类

在另一个类中定义的类称为**内部类**或嵌套类。如果一个对象是使用子类创建的，意味着内部类，那么该对象也可以被父类或根类使用。父类可以有一个或多个内部类，但通常避免使用内部类。

通过使用内部类，我们可以使我们的代码更加面向对象。该类的单个对象可以容纳多个子对象。我们可以使用多个子对象来给我们的程序一个好的结构。

**示例–**

首先我们创建一个类，然后创建该类的构造函数。

在创建一个类之后，我们将在该类中创建另一个类，另一个类中的类将被称为内部类。

```py
# create a Color class
class Color:

  # constructor method
  def __init__(self):
    # object attributes
    self.name = 'Green'
    self.lg = self.Lightgreen()

  def show(self):
    print("Name:", self.name)

  # create Lightgreen class
  class Lightgreen:
     def __init__(self):
        self.name = 'Light Green'
        self.code = '024avc'

     def display(self):
        print("Name:", self.name)
        print("Code:", self.code)

# create Color class object
outer = Color()

# method calling
outer.show()

# create a Lightgreen 
# inner class object
g = outer.lg

# inner class method calling
g.display()
```

**输出:**

```py
 Green
Name:Green

Light Green
023gfd

Name: Light Green
Code: 023gfd
```

## 为什么是内班？

用于两个或多个类的分组。假设我们有两类遥控器和电池。每个遥控器都需要电池，但是没有遥控器的电池就不能用了。因此，我们将电池作为遥控器的内部类别。它帮助我们保存代码。

借助于内部类或嵌套类，我们可以对外部世界隐藏内部类。因此，隐藏代码是内部类的另一个好特性。

通过使用内部类，我们可以很容易地理解类，因为类是密切相关的。我们不需要在整个代码中搜索类，它们几乎都在一起。

虽然内部类或嵌套类在 Python 中没有被广泛使用，但是实现代码将是一个更好的特性，因为当我们使用内部类或嵌套类时，它会直接组织起来。

**语法:**

```py
# create NameOfOuterClass class
class NameOfOuterClass:

  # Constructor method of outer class
  def __init__(self):  

    self.NameOfVariable = Value

    # create Inner class object
    self.NameOfInnerClassObject = self.NameOfInnerClass() 

  # create a NameOfInnerClass class
  class NameOfInnerClass:  
     # Constructor method of inner class
    def __init__(self): 
      self.NameOfVariable = Value

# create object of outer class
outer = NameOfOuterClass() 

```

**内部类的类型–**

*   多重内部类
*   多级内部类

### 多重内部类

该类包含一个或多个内部类，称为多个内部类。我们可以在一个类中有多个内部类，很容易实现多个内部类。

**多个内部类示例–**

```py
# create outer class
class Doctors:  
  def __init__(self):
     self.name = 'Doctor'
     self.den = self.Dentist()
     self.car = self.Cardiologist()

  def show(self):
    print('In outer class')
    print('Name:', self.name)

   # create a 1st Inner class
   class Dentist:   
      def __init__(self):
         self.name = 'Dr. Savita'
         self.degree = 'BDS'
      def display(self):
         print("Name:", self.name)
         print("Degree:", self.degree)

   # create a 2nd Inner class
   class Cardiologist:
      def __init__(self):
         self.name = 'Dr. Amit'
         self.degree = 'DM'
     def display(self):
         print("Name:", self.name)
         print("Degree:", self.degree)

# create a object
# of outer class
outer = Doctors()
outer.show()

# create a object
# of 1st inner class
d1 = outer.den

# create a object
# of 2nd inner class
d2 = outer.car
print()
d1.display()
print()
d2.display()
```

**输出:**

```py
In outer class
Name: Doctor

In inner class 1
Name: Dr. Savita
Degree: BDS

In inner class 2
Name: Dr. Amit
Degree: DM 
```

### 多级内部类

该类包含内部类，而该内部类又包含另一个内部类，这种层次结构称为多级内部类。

**多级内部类示例–**

```py
# create a outer class
class Geeksforgeeks:  

  def __init__(gfg):
     # create a inner class object
     self.inner = self.Inner()

  def show(gfg):
     print('This is an outer class')

  # create a 1st inner class 
  class Inner:

   def __init__(self):
     # create a inner class of inner class object
     self.innerclassofinner = self.Innerclassofinner()

   def show(self):
    print('This is the inner class')

   # create a inner class of inner
   class Innerclassofinner:

      def show(self):
         print()

      def show(self):
         print('This is an inner class of inner class')

# create a outer class object 
# i.e.Geeksforgeeks class object
outer = Geeksforgeeks()
outer.show()
print()

# create a inner class object 
gfg1 = outer.inner
gfg1.show()
print()

# create a inner class of inner class object
gfg2 = outer.inner.innerclassofinner
gfg2.show()
```

**输出:**

> 这是一个外班
> 
> 这是一个内部类
> 
> 这是一个内部类，内部类意味着多级内部类