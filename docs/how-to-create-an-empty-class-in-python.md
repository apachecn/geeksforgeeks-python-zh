# 如何在 Python 中创建一个空类？

> 原文:[https://www . geesforgeks . org/如何在 python 中创建空类/](https://www.geeksforgeeks.org/how-to-create-an-empty-class-in-python/)

一个[类](https://www.geeksforgeeks.org/python-classes-and-objects/)是一个用户定义的蓝图或原型，从它可以创建对象。类可以被视为用户定义的数据类型。通常，类包含被称为类属性的数据成员和用于修改类属性的成员函数。但是你有没有想过如何定义一个空类，即没有成员和成员函数的类？

在 Python 中，如果我们写类似下面这样的东西，它会引发`SyntaxError`。

```
# Incorrect empty class in 
# Python

class Geeks:
```

**输出:**

```
  File "gfg.py", line 5

                ^
SyntaxError: unexpected EOF while parsing

```

在 Python 中，要编写一个空类`pass` 语句。`pass`是 Python 中的一个特殊语句，不做任何事情。它只是作为一个伪语句工作。但是，也可以创建空类的对象。

**示例:**

```
# Python program to demonstrate
# empty class

class Geeks:
    pass

# Driver's code
obj = Geeks()

print(obj)
```

**输出:**

```
<__main__.geeks object="" at="">

```

Python 还允许我们设置空类对象的属性。我们还可以为不同的对象设置不同的属性。为了更好的理解，请看下面的例子。

```
# Python program to demonstrate
# empty class

class Employee:
    pass

# Driver's code
# Object 1 details
obj1 = Employee()
obj1.name = 'Nikhil'
obj1.office = 'GeeksforGeeks'

# Object 2 details
obj2 = Employee()
obj2.name = 'Abhinav'
obj2.office = 'GeeksforGeeks'
obj2.phone = 1234567889

# Printing details
print("obj1 Details:")
print("Name:", obj1.name)
print("Office:", obj1.office)
print()

print("obj2 Details:")
print("Name:", obj2.name)
print("Office:", obj2.office)
print("Phone:", obj2.phone)

# Uncommenting this print("Phone:", obj1.phone)
# will raise an AttributeError
```

**输出:**

```
obj1 Details:
Name: Nikhil
Office: GeeksforGeeks

obj2 Details:
Name: Abhinav
Office: GeeksforGeeks
Phone: 1234567889

```

```
Traceback (most recent call last):
  File "gfg.py", line 34, in print("Phone:", obj1.phone)
AttributeError: 'Employee' object has no attribute 'phone' 
```