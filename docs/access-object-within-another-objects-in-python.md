# 在 Python 中访问另一个对象内的对象

> 原文:[https://www . geesforgeks . org/access-object-in-other-objects-in-python/](https://www.geeksforgeeks.org/access-object-within-another-objects-in-python/)

**先决条件:**[**Python 中 OOPs 的基础知识**](https://www.geeksforgeeks.org/python-classes-and-objects/)

在本文中，我们将学习如何在 Python 中访问其他对象中的对象方法和属性。如果我们有两个不同的类，其中一个在调用构造函数时定义了另一个类。然后，第一类对象可以访问另一个类的方法和属性(即；对象内的对象)。

在下面的例子中，我们学习访问对象中的对象(它的方法和属性)。我们用适当的定义定义了两个类(第一类和第二类)。

*   第一类由一个构造函数和一个方法组成。
*   构造函数在第一个类的属性中形成第二个类的对象。
*   方法定义了第一类方法中的存在。
*   同样，第二个类由一个构造函数和一个方法组成。
*   构造函数形成一个属性。
*   方法定义第二类方法中的存在。

因为第一类的属性作为第二类的对象工作，所以第二类的所有方法和属性都可以使用这个:

```
object_of_first_class.attribute_of_first_class

```

下面是实现:

## 蟒蛇 3

```
# python program to understand the 
# accessing of objects within objects

# define class first
class first:

    # constructor
    def __init__(self):
        # class second object
        # is created
        self.fst = second()

    def first_method(self):
        print("Inside first method")

# define class second
class second:

    # constructor
    def __init__(self):
        self.snd = "GFG"

    def second_method(self):
        print("Inside second method")

# make object of first class
obj1 = first()
print(obj1)

# make object of second class
# with the help of first
obj2 = obj1.fst
print(obj2)

# access attributes and methods 
# of second class
print(obj2.snd)

obj2.second_method()

# This code is contributed
# by Deepanshu Rustagi.
```

**输出:**

```
<__main__.first object at 0x7fde6c57b828>
<__main__.second object at 0x7fde6c57b898>
GFG  
Inside second method

```