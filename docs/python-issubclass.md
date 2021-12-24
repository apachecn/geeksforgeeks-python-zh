# Python issubclass()

> 原文:[https://www.geeksforgeeks.org/python-issubclass/](https://www.geeksforgeeks.org/python-issubclass/)

我们知道[继承](https://www.geeksforgeeks.org/inheritance-in-python/)是面向对象编程概念的构建块之一。一个类从另一个类中派生或继承属性的能力。它还提供了代码的可重用性。我们不必一次又一次地编写相同的代码。此外，它允许我们在不修改类的情况下向类添加更多的特性。

> **参考下面的文章，了解 Python 中 OOPs 和继承的概念。**
> 
> *   [Python 中的面向对象编程](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-1-class-and-its-members/)
> *   [Python 中的继承](https://www.geeksforgeeks.org/inheritance-in-python/)

## Python issubclass()

Python `issubclass()`是用来检查一个类是否是另一个类的子类的内置函数。如果给定的类是给定类的子类，该函数返回`True`，否则返回`False`。

> **语法:** issubclass(对象，classinfo)
> 
> **参数:**
> **对象:**要检查的类
> **类信息:**类、类型或类和类型的元组
> 
> **返回类型:**如果对象是类的子类，或者元组的任何元素，则返回真，否则返回假。

**示例:**

```
# Python program to demonstrate
# issubclass()

# Defining Parent class
class Vehicles:

    # Constructor
    def __init__(vehicleType):
        print('Vehicles is a ', vehicleType)

# Defining Child class
class Car(Vehicles):

    # Constructor
    def __init__(self):
        Vehicles.__init__('Car')

# Driver's code   
print(issubclass(Car, Vehicles))
print(issubclass(Car, list))
print(issubclass(Car, Car))
print(issubclass(Car, (list, Vehicles)))
```

**输出:**

```
True
False
True
True

```

**注意:**不要混淆`isinstance()`和`issubclass()`，因为这两种方法非常相似。然而，名称本身解释了差异。`isinstance()`检查对象是否是 classinfo 的实例或子类。而`issubclass()`只检查是否是 classinfo 的子类(不检查对象关系)。