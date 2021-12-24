# 在 Python 中动态创建类

> 原文:[https://www . geesforgeks . org/create-class-dynamic-in-python/](https://www.geeksforgeeks.org/create-classes-dynamically-in-python/)

类定义实例变量和方法的集合来指定对象类型。一个类可以用来根据需要创建任意多的对象类型的对象实例。对象是具有特定属性(数据成员)和行为(成员函数)的标识实体。具有相似特征和行为的一组对象是同一类的实例。

Python 是一种动态编程语言，由于其灵活性，Python 比静态类型的语言具有显著的优势。Python 代码可以动态导入，类可以在运行时动态创建。

可以使用 Python 中的`type()`函数动态创建类。`type()`功能用于返回对象的类型。

**语法:**

```
type(object)

```

上述语法返回对象的类型。

**示例:**

```
# program to illustrate the use of type()

print(type("Geeks4Geeks !")) 
print(type(1706256))
```

**输出:**

```
class 'str'
class 'int'

```

## 用 Python 创建动态类

可以使用以下语法动态创建类:
**语法:**

```
type(name, bases, attributes) 

Parameters:
name: The user defined name of the class
bases: A list of base classes, and its type is tuple
attributes: the data members and methods contained in the class

```

上面的语法返回了一个新类型的对象。

**示例:**

```
# program to create class dynamically

# constructor
def constructor(self, arg):
    self.constructor_arg = arg

# method
def displayMethod(self, arg):
    print(arg)

# class method
@classmethod
def classMethod(cls, arg):
    print(arg)

# creating class dynamically
Geeks = type("Geeks", (object, ), {
    # constructor
    "__init__": constructor,

    # data members
    "string_attribute": "Geeks 4 geeks !",
    "int_attribute": 1706256,

    # member functions
    "func_arg": displayMethod,
    "class_func": classMethod
})

# creating objects
obj = Geeks("constructor argument")
print(obj.constructor_arg)
print(obj.string_attribute)
print(obj.int_attribute)
obj.func_arg("Geeks for Geeks")
Geeks.class_func("Class Dynamically Created !")
```

**输出:**

```
constructor argument
Geeks 4 geeks!
1706256
Geeks for GeeksClass Dynamically Created!

```

在上面的程序中，类`Geeks`是动态创建的，它有一个构造函数。`Geeks`的数据成员为`string_attribute`和`int_attribute`，`Geeks`的成员函数为`displayMethod()`和`classMethod()`。创建类`Geeks`的一个对象`obj`，分配并显示所有数据成员，同时调用`Geeks`的所有成员函数。