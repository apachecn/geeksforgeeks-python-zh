# 在 Python 中打印一个类的对象

> 原文:[https://www . geeksforgeeks . org/print-python 中的一类对象/](https://www.geeksforgeeks.org/print-objects-of-a-class-in-python/)

一个[对象](https://www.geeksforgeeks.org/python-classes-and-objects/)是一个类的实例。一个类就像一个蓝图，而一个实例是一个有实际值的类的副本。当一个类的对象被创建时，这个类被称为实例化。所有实例共享类的属性和行为。但是这些属性值，即状态对于每个对象都是唯一的。一个类可以有任意数量的实例。

> 参考下面的文章，了解 Python 中的类和对象。
> 
> *   [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)

打印对象为我们提供了正在处理的对象的信息。在 C++中，我们可以通过为类添加好友`ostream&`操作符`<<` `(ostream&, const Foobar&)`方法来做到这一点。在 Java 中，我们使用`toString()`方法。在 Python 中，这可以通过使用`__repr__`或`__str__`方法来实现。如果我们需要详细的调试信息，则使用`__repr__`，而`__str__`用于为用户打印字符串版本。

**示例:**

```
# Python program to demonstrate
# object printing

# Defining a class
class Test: 
    def __init__(self, a, b): 
        self.a = a 
        self.b = b 

    def __repr__(self): 
        return "Test a:% s b:% s" % (self.a, self.b) 

    def __str__(self): 
        return "From str method of Test: a is % s, " \ 
              "b is % s" % (self.a, self.b) 

# Driver Code         
t = Test(1234, 5678) 

# This calls __str__() 
print(t) 

# This calls __repr__() 
print([t])
```

**输出:**

```
From str method of Test: a is 1234, b is 5678
[Test a:1234 b:5678]

```

**关于打印的要点:**

*   Python uses `__repr__` method if there is no `__str__` method.

    **示例:**

    ```
    class Test: 
        def __init__(self, a, b): 
            self.a = a 
            self.b = b 

        def __repr__(self): 
            return "Test a:% s b:% s" % (self.a, self.b) 

    # Driver Code         
    t = Test(1234, 5678) 
    print(t)
    ```

    **输出:**

    ```
    Test a:1234 b:5678

    ```

*   If no __repr__ method is defined then the default is used.

    **示例:**

    ```
    class Test: 
        def __init__(self, a, b): 
            self.a = a 
            self.b = b 

    # Driver Code         
    t = Test(1234, 5678) 
    print(t)  
    ```

    **输出:**

    ```
    <__main__.Test object at 0x7f9b5738c550>

    ```