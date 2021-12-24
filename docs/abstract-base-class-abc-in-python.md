# Python 中的抽象基类

> 原文:[https://www . geesforgeks . org/abstract-base-class-ABC-in-python/](https://www.geeksforgeeks.org/abstract-base-class-abc-in-python/)

你有没有想过检查你使用的对象是否符合特定的规范？有必要验证一个对象是否实现了一个给定的方法或属性，尤其是在创建一个库供其他开发人员使用时。开发人员可以使用 [hasattr](https://www.geeksforgeeks.org/python-hasattr-method/) 或 [isinstance](https://www.geeksforgeeks.org/python-isinstance-method/) 方法来检查输入是否符合特定身份。但是有时使用这些方法来检查无数不同的属性和方法是不方便的。

为了解决这个不便，Python 引入了一个名为**抽象基类(abc)** 的概念。在本节中，我们将讨论抽象基类及其重要性。

*   抽象基类
*   声明抽象基类
*   为什么要声明抽象基类？
*   抽象属性
*   内置抽象类

## 抽象基类

抽象基类的主要目标是提供一种标准化的方法来测试对象是否符合给定的规范。它还可以防止任何不覆盖超类中特定方法的实例化子类的尝试。最后，使用抽象类，一个类可以从另一个类派生身份，而不需要任何对象继承。

## 声明抽象基类

Python 有一个名为 abc(抽象基类)的模块，它提供了创建抽象基类的必要工具。首先，您应该理解抽象基类提供的 ABCMeta 元类。规则是每个抽象类都必须使用 ABCMeta 元类。

ABCMeta 元类提供了一个名为 register method 的方法，可以被它的实例调用。通过使用这个注册方法，任何抽象基类都可以成为任意具体类的祖先。让我们通过一个抽象基类的例子来理解这个过程，这个抽象基类将自己注册为 dict 的祖先。

## 蟒蛇 3

```py
import abc

class AbstractClass(metaclass=abc.ABCMeta):
    def abstractfunc(self):
        return None

print(AbstractClass.register(dict))
```

**输出:**

```py
<class 'dict'>
```

在这里，dict 将自己标识为抽象类的子类。让我们检查一下。

## 蟒蛇 3

```py
import abc

class AbstractClass(metaclass=abc.ABCMeta):
    def abstractfunc(self):
        return None

AbstractClass.register(dict)
print(issubclass(dict, AbstractClass))
```

**输出:**

```py
True
```

## 为什么要声明抽象基类？

为了理解声明一个虚拟子类的需要，我们需要考虑一个类似列表的对象的例子，在这个例子中，您不想设置一个只考虑列表或元组的限制。在此之前，让我们看看如何使用 **isinstance** 来检查类的列表或元组。

```py
isinstance([], (list, tuple))

```

如果您只接受列表或元组，则此*是实例*检查符合目的。但这里的情况不同，没有这样的限制。因此，对于使用您的库发送列表或元组之外的其他东西的开发人员来说，这个解决方案是不可扩展的。抽象类的重要性来了。让我们通过下面的代码来理解。

## 蟒蛇 3

```py
import abc

class MySequence(metaclass=abc.ABCMeta):
    pass

MySequence.register(list)
MySequence.register(tuple)

a = [1, 2, 3]
b = ('x', 'y', 'z')

print('List instance:', isinstance(a, MySequence))
print('Tuple instance:', isinstance(b, MySequence))
print('Object instance:', isinstance(object(), MySequence))
```

**输出:**

```py
List instance: True
Tuple instance: True
Object instance: False
```

如您所见，当您执行 isinstance 检查时，列表和元组都返回 true 对于其他对象，它返回 false。让我们考虑一个场景，开发人员期望类对象本身。在上述情况下，isinstance 将返回 false。但是可以通过创建一个自定义类并将其注册到抽象基类来实现。

这里的“我的序列”是库中的一个抽象类。开发人员可以导入它并注册一个自定义类。让我们看看下面的代码。

## 蟒蛇 3

```py
import abc

class MySequence(metaclass=abc.ABCMeta):
    pass

class CustomListLikeObjCls(object):
    pass

MySequence.register(CustomListLikeObjCls)
print(issubclass(CustomListLikeObjCls, MySequence))
```

**输出:**

```py
True
```

在这里，CustomListLikeObjCls 实例通过向 MySequence 注册而被传递给库。因此，实例检查返回真。除了上述方法之外，您还可以使用 register 方法作为装饰器来注册自定义类。让我们看看如何使用**注册方法作为装饰器**。

## 蟒蛇 3

```py
import abc

class MySequence(metaclass=abc.ABCMeta):
    pass

@MySequence.register
class CustomListLikeObjCls(object):
    pass

print(issubclass(CustomListLikeObjCls, MySequence))
```

**输出:**

```py
True
```

使用上面实现的方法注册一个类就可以达到目的。但是，您必须为每个想要的子类进行手动注册。基于特定方法的自动子类化怎么样？。抽象类有一个名为 [__subclasshook__](https://www.geeksforgeeks.org/__subclasscheck__-and-__subclasshook__-in-python/) 的概念来子类化类。

### [_ _ subclass hook _ _](https://www.geeksforgeeks.org/__subclasscheck__-and-__subclasshook__-in-python/)

这是一种由 ABCMeta 定义的特殊魔法方法。必须使用@classmethod 装饰器将 __subclasshook__ 定义为类方法。它接受类以外的另一个位置参数，并可以返回三个值中的任何一个——真、假或未实现。让我们看看下面的实现。

## 蟒蛇 3

```py
import abc

class AbstractClass(metaclass=abc.ABCMeta):
    @classmethod
    def __subclasshook__(cls, other):
        print('subclass hook:', other)
        hookmethod = getattr(other, 'hookmethod', None)
        return callable(hookmethod)

class SubClass(object):
    def hookmethod(self):
        pass

class NormalClass(object):
    hookmethod = 'hook'

print(issubclass(SubClass, AbstractClass))
print(issubclass(NormalClass, AbstractClass))
```

**输出:**

```py
subclass hook: <class '__main__.SubClass'>
True
subclass hook: <class '__main__.NormalClass'>
False
```

从上面的讨论中，您了解了如何自动挂钩子类。现在我们将研究如何避免实例化超类中不覆盖特定方法的子类。这个特性可以通过@abc.abstractmethod 来实现。

### @abc.abstractmethod

@abc.abstractmethod 防止任何不覆盖超类中特定方法的实例化子类的尝试。让我们看看下面的代码:

## 蟒蛇 3

```py
import abc

class AbstractClass(metaclass=abc.ABCMeta):
    @abc.abstractmethod
    def abstractName(self):
        pass

class InvalidSubClass(AbstractClass):
    pass

isc = InvalidSubClass()
```

由于 InvalidSubclass 不会覆盖方法抽象名称，@abc.abstractmethod 会阻止子类实例化，并引发以下错误。

> 回溯(最近一次调用最后一次):
> 文件/home/553d 5199 a 662239 eae3 ff 58 efb 37 b 6 EC . py】，第 11 行，在<模块>中
> isc = InvalidSubClass()
> 类型错误:无法用抽象方法 abstractName 实例化抽象类 InvalidSubClass

让我们看看另一个例子，其中子类覆盖了抽象方法。

## 蟒蛇 3

```py
import abc

class AbstractClass(metaclass=abc.ABCMeta):
    @abc.abstractmethod
    def abstractName(self):
        pass

class ValidSubClass(AbstractClass):
    def abstractName(self):
        return 'Abstract 1'

vc = ValidSubClass()
print(vc.abstractName())
```

**输出:**

```py
Abstract 1
```

接下来，让我们看看如何将属性声明为抽象类。

## 抽象属性

我们可以使用 [@property](https://www.geeksforgeeks.org/python-property-decorator-property/) decorator 和@abc.abstractmethod 将属性声明为抽象类。让我们看看下面的代码。

## 蟒蛇 3

```py
import abc

class AbstractClass(metaclass=abc.ABCMeta):
    @property
    @abc.abstractmethod
    def abstractName(self):
        pass

class ValidSubClass(AbstractClass):
    @property
    def abstractName(self):
        return 'Abstract 1'

vc = ValidSubClass()
print(vc.abstractName)
```

**输出:**

```py
Abstract 1
```

## 内置抽象类

Python 3 标准库为抽象和非抽象方法提供了一些内置的抽象类。这些包括序列、可变序列、可迭代等等。它通常作为一个内置 Python 类子类化的替代方法。例如，子类化可变序列可以替代列表或字符串的子类化。使用抽象类的主要目的是允许您考虑一种常见的集合类型，而不是为每种类型的集合编码。在这里，我们将讨论单一方法作业成本法和替代集合作业成本法。

*   单一方法作业成本
*   替代-收集作业成本

### 单一方法作业成本

Python 有五个抽象基类。它们如下:

*   可调用(__call__)
*   容器(__ 包含 _ _)
*   Hashable (__hash_)
*   可迭代(__iter_)
*   大小(_len__)

这些抽象基类各包含一个抽象方法。让我们考虑一个 __len__ 方法的例子。

## 蟒蛇 3

```py
from collections.abc import Sized

class SingleMethod(object):
    def __len__(self):
        return 10

print(issubclass(SingleMethod, Sized))
```

**输出:**

```py
True
```

任何具有适当方法的类都被认为是抽象基类的子类。在以上五个抽象基类中，迭代器略有不同。它为 [__iter__](https://www.geeksforgeeks.org/python-__iter__-__next__-converting-object-iterator/) 提供了一个实现，并添加了一个名为 [__next__](https://www.geeksforgeeks.org/python-__iter__-__next__-converting-object-iterator/) 的抽象方法。

### 替代-收集作业成本

可选集合 ABCs 是内置的抽象基类，用于标识子类，这些子类具有相似的用途。它们可以分为三类。让我们一个一个来看。

*   **序列和可变序列**:序列和可变序列是抽象基类，一般表现为元组或列表。序列抽象基类需要 [__getitem__](https://www.geeksforgeeks.org/__getitem__-in-python/) 和 __len__，而可变序列需要 [__setitem__](https://www.geeksforgeeks.org/__getitem__-and-__setitem__-in-python/) 和 [__getitem__](https://www.geeksforgeeks.org/__getitem__-in-python/) 。
*   **映射**:映射自带可变映射，主要针对字典类对象
*   **集合**:该集合带有一个可变集合，用于无序集合。

## 摘要

抽象类的主要目的是检查对象是否符合特定的协议。它是一个有价值的类，用于测试类的某些属性或测试类本身。然而，抽象类没有检查许多其他的东西。其中一些是签名、返回类型等。另一个优点是，它为开发人员测试常见类型的集合提供了一种灵活的方法。