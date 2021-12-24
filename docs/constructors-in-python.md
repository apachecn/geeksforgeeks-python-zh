# Python 中的构造函数

> 原文:[https://www.geeksforgeeks.org/constructors-in-python/](https://www.geeksforgeeks.org/constructors-in-python/)

**先决条件:**Python 中面向对象的[编程](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-1-class-and-its-members/)，Python 中面向对象的[编程|集合 2](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-2-data-hiding-and-object-printing/)
构造函数一般用于实例化一个对象。构造函数的任务是在创建类的对象时初始化(赋值)类的数据成员。在 Python 中，__init__()方法被称为构造函数，并且总是在创建对象时调用。
**构造函数声明语法:**

```py
def __init__(self):
    # body of the constructor
```

**施工人员类型:**

*   **默认构造函数:**默认构造函数是不接受任何参数的简单构造函数。它的定义只有一个参数，这个参数是对正在构造的实例的引用。
*   **参数化构造函数:**带参数的构造函数称为参数化构造函数。参数化构造函数将其第一个参数作为对被构造的名为 self 的实例的引用，其余参数由程序员提供。

**默认构造函数示例:**

## 蟒蛇 3

```py
class GeekforGeeks:

    # default constructor
    def __init__(self):
        self.geek = "GeekforGeeks"

    # a method for printing data members
    def print_Geek(self):
        print(self.geek)

# creating object of the class
obj = GeekforGeeks()

# calling the instance method using the object obj
obj.print_Geek()
```

**输出:**

```py
GeekforGeeks
```

**参数化构造函数** **示例:**

## 蟒蛇 3

```py
class Addition:
    first = 0
    second = 0
    answer = 0

    # parameterized constructor
    def __init__(self, f, s):
        self.first = f
        self.second = s

    def display(self):
        print("First number = " + str(self.first))
        print("Second number = " + str(self.second))
        print("Addition of two numbers = " + str(self.answer))

    def calculate(self):
        self.answer = self.first + self.second

# creating object of the class
# this will invoke parameterized constructor
obj = Addition(1000, 2000)

# perform Addition
obj.calculate()

# display result
obj.display()
```

**输出:**

```py
First number = 1000
Second number = 2000
Addition of two numbers = 3000
```