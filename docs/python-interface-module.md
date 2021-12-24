# Python-接口模块

> 原文:[https://www.geeksforgeeks.org/python-interface-module/](https://www.geeksforgeeks.org/python-interface-module/)

在像 Python 这样的面向对象语言中，接口是应该由实现类提供的方法签名的集合。实现接口是编写有组织的代码和实现抽象的一种方式。

包 **zope.interface** 为 Python 提供了一个“对象接口”的实现。它由 Zope 工具包项目维护。该包直接导出两个对象“接口”和“属性”。它还导出了几个助手方法。它旨在提供比 Python 内置的 abc 模块更严格的语义和更好的错误消息。

## 声明接口

在 python 中，接口是使用 python 类语句定义的，是**接口的子类。接口**，是所有接口的父接口。

```
Syntax : 
class IMyInterface(zope.interface.Interface):
    # methods and attributes

```

**例**

```
import zope.interface

class MyInterface(zope.interface.Interface):
    x = zope.interface.Attribute("foo")
    def method1(self, x):
        pass
    def method2(self):
        pass

print(type(MyInterface))
print(MyInterface.__module__)
print(MyInterface.__name__)

# get attribute
x = MyInterface['x']
print(x)
print(type(x))
```

**输出:**

```
<class zope.interface.interface.InterfaceClass>
__main__
MyInterface
<zope.interface.interface.Attribute object at 0x00000270A8C74358>
<class 'zope.interface.interface.Attribute'>

```

## 实现接口

接口作为设计类的蓝图，所以接口是使用类上的**实现器**装饰器来实现的。如果一个类实现了一个接口，那么这个类的实例就提供了这个接口。对象可以直接提供接口，除了它们的类实现什么。

```
Syntax : 
@zope.interface.implementer(*interfaces)
class Class_name:
    # methods
```

**例**

```
import zope.interface

class MyInterface(zope.interface.Interface):
    x = zope.interface.Attribute("foo")
    def method1(self, x):
        pass
    def method2(self):
        pass

@zope.interface.implementer(MyInterface)
class MyClass:
    def method1(self, x):
        return x**2
    def method2(self):
        return "foo"
```

我们声明我的类实现了我的接口。这意味着我的类的实例提供了我的接口。

## 方法

*   **由(类)实现–**返回一个布尔值，如果类实现接口则为真，否则为假
*   **providedBy(对象)–**返回一个布尔值，如果对象提供接口，则返回 True，否则返回 False
*   **providedBy(类)–**返回 False，因为类不提供接口，但实现接口
*   **list(Zope . interface . implemented by(class))–**返回一个类实现的接口列表
*   **list(Zope . interface . providedby(object))–**返回一个对象提供的接口列表。
*   **列表(Zope . interface . providedby(class))–**返回空列表，因为类不提供接口，但是
    实现了。

```
import zope.interface

class MyInterface(zope.interface.Interface):
    x = zope.interface.Attribute('foo')
    def method1(self, x, y, z):
        pass
    def method2(self):
        pass

@zope.interface.implementer(MyInterface)
class MyClass:
    def method1(self, x):
        return x**2
    def method2(self):
        return "foo"
obj = MyClass()

# ask an interface whether it 
# is implemented by a class:
print(MyInterface.implementedBy(MyClass))

# MyClass does not provide 
# MyInterface but implements it:
print(MyInterface.providedBy(MyClass))

# ask whether an interface
# is provided by an object:
print(MyInterface.providedBy(obj))

# ask what interfaces are 
# implemented by a class:
print(list(zope.interface.implementedBy(MyClass)))

# ask what interfaces are
# provided by an object:
print(list(zope.interface.providedBy(obj)))

# class does not provide interface
print(list(zope.interface.providedBy(MyClass)))
```

**输出:**

```
True
False
True
[<InterfaceClass __main__.MyInterface>]
[<InterfaceClass __main__.MyInterface>]
[]

```

## 接口继承

接口可以通过将其他接口列为基接口来扩展其他接口。

### 功能

*   **扩展(接口)–**返回布尔值，一个接口是否扩展另一个接口。
*   **or extends(interface)–**返回布尔值，无论接口是相同的还是一个扩展另一个。
*   **ISequalorextendedby(interface)–**返回布尔值，无论接口是相同的还是一个被另一个扩展。

```
import zope.interface

class BaseI(zope.interface.Interface):
    def m1(self, x):
        pass
    def m2(self):
        pass

class DerivedI(BaseI):
    def m3(self, x, y):
        pass

@zope.interface.implementer(DerivedI)
class cls:
    def m1(self, z):
        return z**3
    def m2(self):
        return 'foo'
    def m3(self, x, y):
        return x ^ y

# Get base interfaces
print(DerivedI.__bases__)

# Ask whether baseI extends 
# DerivedI
print(BaseI.extends(DerivedI))

# Ask whether baseI is equal to
# or is extended by DerivedI
print(BaseI.isEqualOrExtendedBy(DerivedI))

# Ask whether baseI is equal to
# or extends DerivedI
print(BaseI.isOrExtends(DerivedI))

# Ask whether DerivedI is equal
# to or extends BaseI
print(DerivedI.isOrExtends(DerivedI))
```

**输出:**

```
(<InterfaceClass __main__.BaseI>, )
False
True
False
True

```