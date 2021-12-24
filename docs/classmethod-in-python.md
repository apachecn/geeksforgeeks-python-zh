# Python 中的 classmethod()

> 原文:[https://www.geeksforgeeks.org/classmethod-in-python/](https://www.geeksforgeeks.org/classmethod-in-python/)

**classmethod()** 是 Python 中的一个内置函数，它为给定的函数返回一个类方法。；

> **语法:** classmethod(函数)
> 
> **参数:**该函数接受函数名作为参数。
> 
> **返回类型:**该函数返回转换后的类方法。

您也可以使用@classmethod 装饰器来定义 classmethod。

**语法:**

```
@classmethod
   def fun(cls, arg1, arg2, ...):
```

**在哪里，**

*   **趣味:**需要转换成类方法的函数
*   **返回:**函数的类方法。

classmethod()方法绑定到类，而不是对象。类和对象都可以调用类方法。这些方法可以用类或对象调用。

## **类方法 vs 静态方法**

*   类方法将 cls 作为第一个参数，而静态方法不需要特定的参数。
*   类方法可以访问或修改类状态，而静态方法不能访问或修改它。
*   一般来说，静态方法对类状态一无所知。它们是实用类型的方法，采用一些参数并处理这些参数。另一方面，类方法必须有类作为参数。
*   我们在 python 中使用@classmethod decorator 创建一个类方法，在 python 中使用@staticmethod decorator 创建一个静态方法。

## Python 中的类方法示例

### 示例 1:创建一个简单的类方法

在这个例子中，我们将看到如何创建 classmethod，为此，我们创建了一个名为 geeks 的类，并创建了一个打印对象的函数。

现在，我们将方法 geeks.purchase 传递到 classmethod，该方法将方法转换为类方法，然后我们调用类函数 purchase，而不创建函数对象。

## 蟒蛇 3

```
class geeks:
    course = 'DSA'

    def purchase(obj):
        print("Puchase course : ", obj.course)

geeks.purchase = classmethod(geeks.purchase)
geeks.purchase()
```

**输出:**

```
Puchase course :  DSA
```

### **示例 2:** 使用 class method()创建类方法

## 蟒蛇 3

```
# Python program to understand the classmethod

class Student:

    # create a variable
    name = "Geeksforgeeks"

    # create a function
    def print_name(obj):
        print("The name is : ", obj.name)

# create print_name classmethod
# before creating this line print_name()
# It can be called only with object not with class
Student.print_name = classmethod(Student.print_name)

# now this method can be called as classmethod
# print_name() method is called a class method
Student.print_name()
```

**输出:**

```
The name is :  Geeksforgeeks
```

### **例 3:使用类方法的工厂方法**

classmethod()函数的使用在工厂设计模式中使用，在工厂设计模式中，我们希望使用类名而不是对象来调用许多函数。

## 蟒蛇 3

```
# Python program to demonstrate
# use of a class method and static method.
from datetime import date

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # a class method to create a
    # Person object by birth year.
    @classmethod
    def fromBirthYear(cls, name, year):
        return cls(name, date.today().year - year)

    def display(self):
        print("Name : ", self.name, "Age : ", self.age)

person = Person('mayank', 21)
person.display()
```

**输出:**

```
Name :  mayank Age :  21
```

## **@ class method Decorator**

@classmethod 装饰器是一个内置的[函数装饰器](https://www.geeksforgeeks.org/function-decorators-in-python-set-1-introduction/)，它是一个在您的函数被定义之后得到评估的表达式。评估的结果会影响您的函数定义。

类方法接收类作为隐式的第一个参数，就像实例方法接收实例一样。

**语法:**

```
class C(object):
    @classmethod
    def fun(cls, arg1, arg2, ...):
       ....
```

哪里，

*   **趣味:**需要转换成类方法的函数
*   **返回:**函数的类方法。

**注:**

*   类方法是绑定到类而不是类的对象的方法。
*   他们可以访问类的状态，因为它采用指向类而不是对象实例的类参数。
*   它可以修改适用于该类所有实例的类状态。例如，它可以修改适用于所有实例的类变量。

在下面的例子中，我们使用 staticmethod()和 classmethod()来检查一个人是否是成年人。

## 计算机编程语言

```
# Python program to demonstrate
# use of a class method and static method.
from datetime import date

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # a class method to create a
    # Person object by birth year.
    @classmethod
    def fromBirthYear(cls, name, year):
        return cls(name, date.today().year - year)

    # a static method to check if a
    # Person is adult or not.
    @staticmethod
    def isAdult(age):
        return age > 18

person1 = Person('mayank', 21)
person2 = Person.fromBirthYear('mayank', 1996)

print(person1.age)
print(person2.age)

# print the result
print(Person.isAdult(22))
```

**输出:**

```
21
25
True
```