# Python:调用父类方法

> 原文:[https://www . geesforgeks . org/python-call-parent-class-method/](https://www.geeksforgeeks.org/python-call-parent-class-method/)

类是用户定义的蓝图或原型，从中创建对象。类提供了一种将数据和功能捆绑在一起的方法。创建一个新类会创建一个新类型的对象，从而允许创建该类型的新实例。

**示例:**

```py
# Python program to demonstrate
# classes

class cls:

    # Constructor
    def __init__(self, fname, mname, lname):
        self.firstname = fname
        self.middlename = mname
        self.lastname = lname

    # class Function
    def print(self):
        print(self.firstname, self.middlename, self.lastname)

# Use the Parent class to create an object
# and then execute the print method:
x = cls("Geeks", "for", "Geeks")
x.print()
```

**输出:**

```py
Geeks for Geeks

```

## 调用父类方法

要了解父类的概念，你必须了解 Python 中的[继承](https://www.geeksforgeeks.org/inheritance-in-python/)。简单来说，继承是一个类(通常称为子类或子类)从另一个类(通常称为父类或超类)继承属性的概念。

但是你有没有想过在子类的帮助下调用父类中定义的函数？这可以使用 Python 来完成。你只需要创建一个子类的对象，并使用`dot(.)`运算符调用父类的函数。

**示例:**

```py
# Python code to demonstrate 
# parent call method 

class Parent:

    # create a parent class method
    def show(self):
        print("Inside Parent class")

# create a child class
class Child(Parent):

    # Create a child class method
    def display(self):
        print("Inside Child class")

# Driver's code
obj = Child()
obj.display()

# Calling Parent class
obj.show()
```

**输出**

```py
Inside Child class
Inside Parent class

```

#### 在方法重写后调用父类方法

方法重写是任何面向对象编程语言的一种能力，它允许子类或子类提供某个方法的特定实现，而该方法已经由其超类或父类之一提供。

父类方法也可以在重写的方法中调用。这通常可以通过两种方式实现。

*   **Using Classname:** Parent’s class methods can be called by using the Parent `classname.method` inside the overridden method.

    **示例:**

    ```py
    # Python program to demonstrate
    # calling the parent's class method
    # inside the overridden method

    class Parent():

        def show(self):
            print("Inside Parent")

    class Child(Parent):

        def show(self):

            # Calling the parent's class
            # method
            Parent.show(self)
            print("Inside Child")

    # Driver's code
    obj = Child()
    obj.show()
    ```

    **输出:**

    ```py
    Inside Parent
    Inside Child

    ```

*   **Using Super():** Python `super()` function provides us the facility to refer to the parent class explicitly. It is basically useful where we have to call superclass functions. It returns the proxy object that allows us to refer parent class by ‘super’.

    **例 1:**

    ```py
    # Python program to demonstrate
    # calling the parent's class method
    # inside the overridden method using
    # super()

    class Parent():

        def show(self):
            print("Inside Parent")

    class Child(Parent):

        def show(self):

            # Calling the parent's class
            # method
            super().show()
            print("Inside Child")

    # Driver's code
    obj = Child()
    obj.show()
    ```

    **输出:**

    ```py
    Inside Parent
    Inside Child

    ```

    **例 2:**

    ```py
    # Program to define the use of super() 
    # function in multiple inheritance 
    class GFG1: 
        def __init__(self): 
            print('HEY !!!!!! GfG I am initialised(Class GEG1)') 

        def sub_GFG(self, b): 
            print('Printing from class GFG1:', b) 

    # class GFG2 inherits the GFG1 
    class GFG2(GFG1): 
        def __init__(self): 
            print('HEY !!!!!! GfG I am initialised(Class GEG2)') 
            super().__init__() 

        def sub_GFG(self, b): 
            print('Printing from class GFG2:', b) 
            super().sub_GFG(b + 1) 

    # class GFG3 inherits the GFG1 ang GFG2 both 
    class GFG3(GFG2): 
        def __init__(self): 
            print('HEY !!!!!! GfG I am initialised(Class GEG3)') 
            super().__init__() 

        def sub_GFG(self, b): 
            print('Printing from class GFG3:', b) 
            super().sub_GFG(b + 1) 

    # main function 
    if __name__ == '__main__': 

        # created the object gfg 
        gfg = GFG3() 

        # calling the function sub_GFG3() from class GHG3 
        # which inherits both GFG1 and GFG2 classes 
        gfg.sub_GFG(10)
    ```

    **输出:**

    ```py
    HEY !!!!!! GfG I am initialised(Class GEG3)
    HEY !!!!!! GfG I am initialised(Class GEG2)
    HEY !!!!!! GfG I am initialised(Class GEG1)
    Printing from class GFG3: 10
    Printing from class GFG2: 11
    Printing from class GFG1: 12

    ```