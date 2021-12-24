# Python 中属性和属性的区别

> 原文:[https://www . geesforgeks . org/python 中属性和属性的区别/](https://www.geeksforgeeks.org/difference-between-attributes-and-properties-in-python/)

**类属性:**类属性对于每个类都是唯一的。该类的每个实例都将具有此属性。

**示例:**

## 蟒蛇 3

```py
# declare a class
class Employee: 

    # class attribute
    count = 0      

    # define a method
    def increase(self): 
        Employee.count += 1

# create an Employee 
# class object
a1 = Employee() 

# calling object's method
a1.increase() 

# print value of class attribute
print(a1.count) 

a2 = Employee() 

a2.increase() 

print(a2.count) 

print(Employee.count)
```

**输出:**

```py
1
2
2

```

在上面的例子中，计数变量是一个类属性。

**实例属性:**实例属性对于每个实例都是唯一的，(实例是对象的另一个名称)。每个对象/实例都有自己的属性，可以在不影响其他实例的情况下进行更改。

**示例:**

## 蟒蛇 3

```py
# create a class
class Employee: 

    # constructor
    def __init__(self): 

        # instance attribute
        self.name = 'Gfg'
        self.salary = 4000

    # define a method
    def show(self): 
        print(self.name) 
        print(self.salary) 

# create an object of 
# Employee class
x = Employee()

# method calling
x.show()
```

**输出:**

```py
Gfg
4000

```

现在，让我们看一个关于属性的例子:

1)使用**属性()**函数创建类的属性:

> **语法:**属性(fget，fset，fdel，doc)

**示例:**

## 蟒蛇 3

```py
# create a class
class gfg: 

    # constructor
    def __init__(self, value): 
        self._value = value 

    # getting the values 
    def getter(self): 
        print('Getting value') 
        return self._value 

    # setting the values 
    def setter(self, value): 
        print('Setting value to ' + value) 
        self._value = value 

    # deleting the values 
    def deleter(self): 
        print('Deleting value') 
        del self._value 

    # create a properties
    value = property(getter, setter, deleter, ) 

# create a gfg class object
x = gfg('Happy Coding!') 
print(x.value) 

x.value = 'Hey Coder!'

# deleting the value
del x.value
```

**输出:**

```py
Getting value
Happy Coding!
Setting value to Hey Coder!
Deleting value

```

2) 使用 **@property** 装饰器创建类的属性:

我们可以使用@property decorator 应用属性函数。这是内置的装饰器之一。装饰器只是一个函数，它将另一个函数作为参数，并通过包装来增加它的行为。

**示例:**

## 蟒蛇 3

```py
# create a class
class byDeco: 

   # constructor
    def __init__(self, value): 
        self._value = value 

    # getting the values
    @property              
    def value(self): 
        print('Getting value') 
        return self._value 

    # setting the values     
    @value.setter 
    def value(self, value): 
        print('Setting value to ' + value) 
        self._value = value 

    # deleting the values 
    @value.deleter 
    def value(self): 
        print('Deleting value') 
        del self._value 

# create an object of class
x = byDeco('happy Coding') 
print(x.value) 

x.value = 'Hey Coder!'

# deleting the value
del x.value
```

**输出:**

```py
Getting value
happy Coding
Setting value to Hey Coder!
Deleting value
```

## 属性属性差异表

<figure class="table">

| 

**属性**

 | 

**属性**

 |
| --- | --- |
| 属性由数据变量描述，例如姓名、年龄、身高等。 | 属性是一种特殊的属性。 |
| 两种类型的属性:

*   类别属性
*   实例属性

 | 它有 getter、setter 和 delete 方法，如 __get__ 方法、__set__ 方法和 __delete__ 方法。 |
| [**类属性**](https://www.geeksforgeeks.org/g-fact-34-class-or-static-variables-in-python/) 定义在类体部分通常在顶部。 | 我们可以使用 [**属性()**](https://www.geeksforgeeks.org/python-property-function/) 功能定义获取器、设置器和删除方法。 |
| **I**[**instance 属性**](https://www.geeksforgeeks.org/class-instance-attributes-python/) 是在类体中使用 **self** 关键字定义的通常它采用 **__init__()** 方法。 | 如果我们只想读取属性，还有一个 [**@property**](https://www.geeksforgeeks.org/python-property-decorator-property/) 装饰器，你可以在你的方法上面添加。 |

</figure>