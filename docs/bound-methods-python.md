# 绑定方法 python

> 原文:[https://www.geeksforgeeks.org/bound-methods-python/](https://www.geeksforgeeks.org/bound-methods-python/)

绑定方法是依赖于类的实例作为第一个参数的方法。它将实例作为用于访问变量和函数的第一个参数传递。在 Python 3 和更高版本的 Python 中，类中的所有函数默认都是绑定方法。

让我们用一个例子来理解这个概念:

```
# Python code to demonstrate
# use of bound methods

class A:

    def func(self, arg):
        self.arg = arg
        print("Value of arg = ", arg)

# Creating an instance
obj = A()  

# bound method
print(obj.func)
```

**输出:**

```
< bound method A.func of <__main__.A object at 0x7fb81c5a09e8>>

```

这里，

```
 obj.func(arg) is translated by python as A.func(obj, arg).
```

实例`obj`自动作为第一个参数传递给被调用的函数，因此函数的第一个参数将用于访问对象的变量/函数。

让我们看另一个绑定方法的例子。

```
# Python code to demonstrate
# use of bound methods

class Car:
    # Car class created
    gears = 5

    # a class method to change the number of gears 
    @classmethod
    def change_gears(cls, gears):
        cls.gears = gears

# instance of class Car created
Car1 = Car()

print("Car1 gears before calling change_gears() = ", Car1.gears)
Car1.change_gears(6) 
print("Gears after calling change_gears() = ", Car1.gears)

# bound method
print(Car1.change_gears)
```

**输出:**

```
Car1 gears before calling change_gears() =  5
Gears after calling change_gears() =  6
<bound method Car.change_gears of <class '__main__.Car'>>

```

上面的代码是一个[类方法](https://www.geeksforgeeks.org/classmethod-in-python/)的例子。类方法类似于绑定方法，只是实例的类作为参数传递，而不是实例本身。在上面的例子中，当我们调用`Car1.change_gears(6)`时，类‘Car’作为第一个参数被传递。