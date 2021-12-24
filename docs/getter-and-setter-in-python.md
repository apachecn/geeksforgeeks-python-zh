# Python 中的 Getter 和 Setter

> 原文:[https://www.geeksforgeeks.org/getter-and-setter-in-python/](https://www.geeksforgeeks.org/getter-and-setter-in-python/)

在 Python 中，getters 和 setters 与其他面向对象编程语言中的不同。基本上，在面向对象程序中使用 getters 和 setters 的主要目的是确保数据封装。[python 中的私有变量](https://www.geeksforgeeks.org/private-variables-python/)实际上并不像其他面向对象语言那样是隐藏字段。python 中的 Getters 和 Setters 常用于以下情况:

*   我们使用 getters & setters 来添加关于获取和设置值的验证逻辑。
*   避免直接访问类字段，即外部用户不能直接访问或修改私有变量。

**使用正常功能实现吸杂和沉降行为**

为了实现 getters & setters 属性，如果我们定义正常的`get()`和`set()`方法，它将不会反映任何特殊的实现。例如

```
# Python program showing a use
# of get() and set() method in
# normal function

class Geek:
    def __init__(self, age = 0):
         self._age = age

    # getter method
    def get_age(self):
        return self._age

    # setter method
    def set_age(self, x):
        self._age = x

raj = Geek()

# setting the age using setter
raj.set_age(21)

# retrieving age using getter
print(raj.get_age())

print(raj._age)
```

**输出:**

```
21
21

```

在上面的代码函数中`get_age()`和`set_age()`作为普通函数，不作为获取器和设置器发挥任何影响，为了实现这样的功能 Python 有一个特殊的函数`property()`。

**使用 property()函数实现吸气剂和沉降剂行为**

在 Python 中`property()`是一个创建并返回属性对象的内置函数。属性对象有三种方法，getter()、setter()和 delete()。Python 中的`property()` 函数有四个参数`property(fget, fset, fdel, doc)`，`fget`是一个检索属性值的函数。`fset`是设置属性值的功能。`fdel`是删除属性值的功能。`doc`为属性创建文档字符串。一个属性对象有三种方法，`getter()`、`setter()`、`delete()`分别指定`fget`、`fset`和`fdel`。例如

```
# Python program showing a
# use of property() function

class Geeks:
     def __init__(self):
          self._age = 0

     # function to get value of _age
     def get_age(self):
         print("getter method called")
         return self._age

     # function to set value of _age
     def set_age(self, a):
         print("setter method called")
         self._age = a

     # function to delete _age attribute
     def del_age(self):
         del self._age

     age = property(get_age, set_age, del_age) 

mark = Geeks()

mark.age = 10

print(mark.age)
```

**Output:**

```
setter method called
getter method called
10

```

在上面的代码中，`line #25`只有一个 print 语句，但是由于在`line #23`中调用的 setter 方法`set_age()`和在`line #25`中调用的 getter 方法`get_age()`，输出由三行组成。因此`age`是一个属性对象，有助于保持私有变量的访问安全。

**使用@property 装饰器实现获取和设置行为**

在之前的方法中，我们使用了`property()`函数来实现获取和设置行为。然而，正如本文前面提到的，post getters 和 setters 也用于验证属性值的获取和设置。还有一种方法可以实现属性功能，即使用[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)。Python @property 是内置装饰器之一。任何装饰器的主要目的都是改变你的类方法或属性，这样你的类的用户就不需要在他们的代码中做任何改变。例如

```
# Python program showing the use of
# @property

class Geeks:
     def __init__(self):
          self._age = 0

     # using property decorator
     # a getter function
     @property
     def age(self):
         print("getter method called")
         return self._age

     # a setter function
     @age.setter
     def age(self, a):
         if(a < 18):
            raise ValueError("Sorry you age is below eligibility criteria")
         print("setter method called")
         self._age = a

mark = Geeks()

mark.age = 19

print(mark.age)
```

**输出:**

```
setter method called
getter method called
19

```

在上面的代码中，很清楚如何使用`@property`装饰器以 pythonic 方式创建 getter&setter。`Line 15-16`作为一个验证代码，如果我们试图用小于 18 的值初始化 age，它会引发`ValueError`，这样任何类型的验证都可以应用在 getter 或 setter 函数中。