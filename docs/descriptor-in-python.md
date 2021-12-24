# Python 中的描述符

> 原文:[https://www.geeksforgeeks.org/descriptor-in-python/](https://www.geeksforgeeks.org/descriptor-in-python/)

**描述符的定义:**
Python 描述符被创建来管理使用对象作为参考的不同类的属性。在描述符中，我们使用了三种不同的方法，分别是`__getters__()`、`__setters__()`和`__delete__()`。如果这些方法中的任何一个是为一个对象定义的，它可以被称为描述符。通常，Python 使用像 getters 和 setters 这样的方法来调整属性上的值，而无需任何特殊处理。这只是一个基本的存储系统。有时，您可能需要验证分配给某个值的值。描述符是属性、方法、静态方法、类方法和`super()`背后的机制。

**描述符协议:**
在其他编程语言中，描述符被称为 setter 和 getter，其中公共函数用于获取和设置私有变量。Python 没有私有变量的概念，描述符协议可以被认为是实现类似功能的一种 python 方式。描述符是在 Python 中实现类的一种新方法，它不需要从特定的对象继承任何东西。为了在 python 中轻松实现描述符，我们必须使用至少一种上面定义的方法。请注意，下面的实例返回到访问该属性的对象，而所有者是描述符作为属性被分配到的类。python 描述符中有三个协议，分别是 setters、getters 和 delete 方法。

*   `gfg.__get__(self, obj, type=None)`:当您想要检索信息`(value = obj.attr)`时，这个属性被调用，无论它返回什么，都将被赋予请求该属性值的代码。
*   `gfg.__set__(self, obj, value)`:调用这个方法设置一个属性`(obj.attr = 'value')`的值，它不会给你返回任何东西。
*   `gfg.__delete__(self, obj)`:从对象中删除属性时调用此方法`(del obj.attr)`

**调用描述符:**
每当收到对`set()`方法或`get()`方法的调用时，描述符都会被自动调用。例如，`obj.gfg`在`obj`的字典中查找 gfg。如果 gfg 定义了方法`__get__()`，则调用`gfg.__get__(obj)`。也可以通过方法名直接调用，即`gfg.__get__(obj)`。

```py
# Python program showing
# how to invoke descriptor

def __getattribute__(self, key):
    v = object.__getattribute__(self, key)
    if hasattr(v, '__get__'):
        return v.__get__(None, self)
    return v
```

**需要记住的重点是:**

*   描述符由`__getattribute__()`方法调用。
*   覆盖`__getattribute__()`防止自动描述符调用。
*   `object.__getattribute__()`和`type.__getattribute__()`给`__get__()`打不同的电话。
*   数据描述符总是覆盖实例字典。
*   实例字典可能会覆盖非数据描述符。

**描述符示例:**
在本例中，数据描述符正常设置和返回值，并打印记录其访问的消息。
**代码 1:**

```py
class Descriptor(object):

    def __init__(self, name =''):
        self.name = name

    def __get__(self, obj, objtype):
        return "{}for{}".format(self.name, self.name)

    def __set__(self, obj, name):
        if isinstance(name, str):
            self.name = name
        else:
            raise TypeError("Name should be string")

class GFG(object):
    name = Descriptor()

g = GFG()
g.name = "Geeks"
print(g.name)
```

**输出:**

```py
GeeksforGeeks

```

**代码 2:**

```py
class Descriptor(object):

    def __init__(self, name =''):
        self.name = name

    def __get__(self, obj, objtype):
        return "{}for{}".format(self.name, self.name)

    def __set__(self, obj, name):
        if isinstance(name, str):
            self.name = name
        else:
            raise TypeError("Name should be string")

class GFG(object):
    name = Descriptor()

g = GFG()
g.name = "Computer"
print(g.name)
```

**输出:**

```py
ComputerforComputer

```

**使用属性()创建描述符:**
`[property()](https://www.geeksforgeeks.org/python-property-function/)`，很容易为任何属性创建可用的描述符。创建`property()`的语法

```py
property(fget=None, fset=None, fdel=None, doc=None)
```

```py
# Python program to explain property() function 

# Alphabet class 
class Alphabet: 
    def __init__(self, value): 
        self._value = value 

    # getting the values 
    def getValue(self): 
        print('Getting value') 
        return self._value 

    # setting the values 
    def setValue(self, value): 
        print('Setting value to ' + value) 
        self._value = value 

    # deleting the values 
    def delValue(self): 
        print('Deleting value') 
        del self._value 

    value = property(getValue, setValue, delValue, ) 

# passing the value 
x = Alphabet('GeeksforGeeks') 
print(x.value) 

x.value = 'GfG'

del x.value 
```

**输出:**

```py
Getting value
GeeksforGeeks
Setting value to GfG
Deleting value

```

**使用类方法创建描述符:**
在本例中，我们创建一个类并覆盖任何描述符方法`__set__`、`__ get__`和`__delete__`。当许多不同的类和属性需要相同的描述符时，使用这个方法，例如，类型验证。

```py
class Descriptor(object):

    def __init__(self, name =''):
        self.name = name

    def __get__(self, obj, objtype):
        return "{}for{}".format(self.name, self.name)

    def __set__(self, obj, name):
        if isinstance(name, str):
            self.name = name
        else:
            raise TypeError("Name should be string")

class GFG(object):
    name = Descriptor()

g = GFG()
g.name = "Geeks"
print(g.name)
```

**输出:**

```py
GeeksforGeeks

```

**使用@property Decorator 创建描述符:**
在本例中，我们使用了属性装饰器的能力，它是属性类型方法和 Python 装饰器的组合。

```py
class Alphabet: 
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

# passing the value 
x = Alphabet('Peter') 
print(x.value) 

x.value = 'Diesel'

del x.value 
```

**输出:**

```py
Getting value
Peter
Setting value to Diesel
Deleting value

```