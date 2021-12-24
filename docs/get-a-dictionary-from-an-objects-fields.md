# 从对象字段获取字典

> 原文:[https://www . geesforgeks . org/get-a-dictionary-from-a-objects-field/](https://www.geeksforgeeks.org/get-a-dictionary-from-an-objects-fields/)

在本文中，我们将讨论如何从对象的字段中获取字典，即如何以字典的形式获取类成员。有两种方法可以解决上述问题:

1.  通过在类的对象上使用 __dict__ 属性并获取字典。Python 中的所有对象都有一个属性 __dict__，它是一个字典对象，包含为该对象本身定义的所有属性。属性与其值的映射用于生成字典。
2.  通过调用内置 vars 方法，该方法用于返回模块、类、类实例或对象的 __dict__ 属性。

# **方法 1:** 使用 _ _ dict _ _ 属性从任意对象生成字典:

## 蟒蛇 3

```py
# class Animals is declared
class Animals:

    # constructor
    def __init__(self):

        # keys are initialized with
        # their respective values
        self.lion = 'carnivore'
        self.dog = 'omnivore'
        self.giraffe = 'herbivore'

    def printit(self):
        print("Dictionary from the object fields\
        belonging to the class Animals:")

# object animal of class Animals
animal = Animals()

# calling printit method
animal.printit()
# calling attribute __dict__ on animal
# object and printing it
print(animal.__dict__)
```

**输出:**

> 来自动物类对象字段的字典:
> {“狮子”:“食肉动物”、“狗”:“杂食动物”、“长颈鹿”:“食草动物”}

**#方法 2:** 使用内置 vars 方法从任意对象生成字典:

## 蟒蛇 3

```py
# class A is declared
class A:

    # constructor
    def __init__(self):

        # keys are initialized with 
        # their respective values
        self.A = 1
        self.B = 2
        self.C = 3
        self.D = 4

# object obj of class A
obj = A()

# calling vars method on obj object
print(vars(obj))
```

**输出:**

```py
{'A': 1, 'B': 2, 'C': 3, 'D': 4}

```