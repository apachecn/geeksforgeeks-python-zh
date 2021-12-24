# _ _ Python 中的 init _ subclass _ _ _

> 原文:[https://www.geeksforgeeks.org/__init_subclass__-in-python/](https://www.geeksforgeeks.org/__init_subclass__-in-python/)

**先决条件** : [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)，[Python 中的继承](https://www.geeksforgeeks.org/inheritance-in-python/)

不管任何编程语言，继承都是面向对象编程概念中最重要的主题之一。继承是用另一个类来定义一个类的概念。根据继承，我们知道超类引用可以保存它的子类引用。我们都知道超类的行为可以根据它的子类的实现而改变。

但是现在，我们可以通过使用***_ _ init _ subclass _ _***来改变子类的行为

## __init_subclass__

```py
# defining a SuperClass
class SuperClass:

     # defining __init_subclass__ method
    def __init_subclass__(cls, **kwargs):
        cls.default_name ="Inherited Class"

# defining a SubClass
class SubClass(SuperClass):

     # an attribute of SubClass
    default_name ="SubClass" 
    print(default_name)

subclass = SubClass()
print(subclass.default_name)
```

**输出:**

```py
SubClass
Inherited Class

```

**理解代码**

*   在上面的例子中，有 2 个类(即超类和子类)，子类继承自超类。 **default_name** 是 SubClass 的属性。
*   属性**默认名称**的值由超类使用 **__init_subclass__** 方法更改。
*   *cls* 是指遗传的亚类。给新类的关键字参数(**kwargs)被传递给父类的 __init_subclass__。
*   为了与使用 __init_subclass__ 的其他子类兼容，应该取出所需的关键字参数，并将其他参数传递给基类(超类)。

这个`__init_subclass__`看起来很像 Decorator 类。但是当类装饰器只影响它们所应用到的特定类时，`__init_subclass__`只适用于定义该方法的类的未来子类。这意味着我们可以改变/定义从超类继承的任何新类的行为。
T3】例:

```py
# defining a SuperClass
class SuperClass:
    def __init_subclass__(cls, default_name, **kwargs):
        cls.default_name = default_name

# defining a subclass
class SubClass1(SuperClass, default_name ="SubClass1"):
    pass

# defining another subclass
class SubClass2(SuperClass, default_name ="SubClass2"):
    default_name = "InheritedClass"

# references for subclasses
subClass1 = SubClass1()
subClass2 = SubClass2()

print(subClass1.default_name)
print(subClass2.default_name)
```

**输出:**

```py
SubClass1
SubClass2

```

由此我们可以得出结论 __init_subclass__ 方法用于改变将来可能创建的子类的行为。