# 如何获取 Python 中的类属性列表？

> 原文:[https://www . geesforgeks . org/如何获取 python 中的类属性列表/](https://www.geeksforgeeks.org/how-to-get-a-list-of-class-attributes-in-python/)

类是用户定义的蓝图或原型，从中创建对象。类提供了一种将数据和功能捆绑在一起的方法。创建一个新类会创建一个新类型的对象，从而允许创建该类型的新实例。每个类实例都可以附加属性来维护其状态。类实例也可以有方法(由其类定义)来修改其状态。

**示例:**

```py
# Python program to demonstrate
# classes

class Student:

    # class variable
    stream = "COE"

    # Constructor
    def __init__(self, name, roll_no):

        self.name = name
        self.roll_no = roll_no

# Driver's code
a = Student("Shivam", 3425)
b = Student("Sachin", 3624)

print(a.stream)
print(b.stream)
print(a.name)
print(b.name)

# Class variables can be accessed
# using class name also 
print(Student.stream) 
```

**输出:**

```py
COE
COE
Shivam
Sachin
COE

```

**注意:**更多信息请参考 [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)。

#### 获取类属性列表

了解我们正在使用的属性非常重要。对于小数据，很容易记住属性的名称，但是在处理大数据时，很难记住所有的属性。幸运的是，我们在 Python 中有一些函数可用于此任务。

**方法 1:** 为了获得一个类的所有属性、方法以及一些继承的魔法方法的列表，我们使用了一个名为`dir()`的内置方法。

**示例:**

```py
class Number :

    # Class Attributes
    one = 'first'
    two = 'second'
    three = 'third'

    def __init__(self, attr):
        self.attr = attr

    def show(self): 
        print(self.one, self.two, self.three, self.attr)

n = Number(2)
n.show()

# Passing both the object 
# and class as  argument
# to the dir method
print('\nBy passing object of class')
print(dir(n))

print('\nBy passing class itself ')
print(dir(Number))
```

**输出:**

> 第一第二第三 2
> 
> 通过传递类的对象
> ['__class__ '，' __delattr__ '，' __dict__ '，' __dir__ '，' __doc__ '，' __eq__ '，' __format__ '，' __ge__ '，' __getattribute_ '，' __gt__ '，' __hash_ '，' __init__ '，' __init_subclass__ '，' __le_ '，' __lt__ '，' __ 模块
> 
> 通过传递类本身
> [“_ _ class _ _”、“__delattr__”、“__dict__”、“__dir__”、“__doc__”、“__eq__”、“__format__”、“__ge__”、“__getattribute__”、“__gt__”、“__hash_”、“__init__”、“__init_subclass__”、“__le_”、“__lt__”、“__module__”

**方法 2:** 查找属性列表的另一种方法是使用模块`inspect`。该模块提供了一个名为`getmemebers()`的方法，该方法返回类属性和方法的列表。

**例 1:**

```py
import inspect

class Number :

    # Class Attributes
    one = 'first'
    two = 'second'
    three = 'third'

    def __init__(self, attr):
        self.attr = attr

    def show(self): 
        print(self.one, self.two, self.three, self.attr)

# Driver's code
n = Number(2)
n.show()

# getmembers() returns all the 
# members of an object 
for i in inspect.getmembers(n):

    # to remove private and protected
    # functions
    if not i[0].startswith('_'):

        # To remove other methods that
        # doesnot start with a underscore
        if not inspect.ismethod(i[1]): 
            print(i)
```

**输出:**

```py
first second third 2
('attr', 2)
('one', 'first')
('three', 'third')
('two', 'second')

```

**方法三:**要找属性我们也可以使用魔法法`__dict__`。此方法仅返回实例属性。

**示例:**

```py
class Number :

    # Class Attributes
    one = 'first'
    two = 'second'
    three = 'third'

    def __init__(self, attr):
        self.attr = attr

    def show(self): 
        print(self.one, self.two, self.three, self.attr)

# Driver's code
n = Number(2)
n.show()

# using __dict__ to access attributes
# of the object n along with their values
print(n.__dict__)

# to only access attributes
print(n.__dict__.keys())

# to only access values
print(n.__dict__.values())
```

**输出:**

```py
first second third 2
{'attr': 2}
dict_keys(['attr'])
dict_values([2])

```