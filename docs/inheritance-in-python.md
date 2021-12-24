# Python 中的继承

> 原文:[https://www.geeksforgeeks.org/inheritance-in-python/](https://www.geeksforgeeks.org/inheritance-in-python/)

继承是一个类从另一个类派生或继承属性的能力。继承的好处是:

1.  它很好地代表了现实世界的关系。
2.  它提供了代码的**可重用性**。我们不必一次又一次地编写相同的代码。此外，它允许我们在不修改类的情况下向类添加更多的特性。
3.  它本质上是可传递的，这意味着如果 B 类从另一个 A 类继承，那么 B 的所有子类都将自动从 A 类继承。

下面是 Python 中继承的一个简单例子

## 蟒蛇 3

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

    # To check if this person is an employee
    def isEmployee(self):
        return False

# Inherited or Subclass (Note Person in bracket)
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
Geek1 False
Geek2 True

```