# Python 中的私有变量

> 原文:[https://www.geeksforgeeks.org/private-variables-python/](https://www.geeksforgeeks.org/private-variables-python/)

**先决条件:**[Python 中的下划线](https://www.geeksforgeeks.org/underscore-_-python/)
在 Python 中，不存在“私有”实例变量，除非在对象内部，否则无法访问这些变量。然而，大多数 Python 代码和编码者都遵循一个约定，即以下划线为前缀的名称，例如 **_geek** 应该被视为 API 或任何 Python 代码的非公共部分，无论它是函数、方法还是数据成员。在此过程中，我们还将尝试理解各种形式的尾随[下划线](https://www.geeksforgeeks.org/underscore-_-python/)的概念，例如，for _ in range(10)，__init__(self)。

**芒灵及其工作原理**

在 Python 中，有一种叫做名称 mangling 的东西，这意味着对类私有成员的有效用例的支持是有限的，基本上是为了避免名称与子类定义的名称的名称冲突。任何形式为 __geek 的标识符(至少两个前导下划线或最多一个尾随下划线)都被替换为 _ classname _ _ geek，其中 classname 是当前类名，前导下划线被去除。只要它出现在类的定义中，这种混淆就完成了。这有助于让子类在不中断类内方法调用的情况下重写方法。
让我们看看这个例子，并尝试找出这条下划线是如何工作的:

## 计算机编程语言

```py
# Python code to illustrate how mangling works
class Map:
    def __init__(self, iterate):
        self.list = []
        self.__geek(iterate)
    def geek(self, iterate):
        for item in iterate:
            self.list.append(item)

    # private copy of original geek() method
    __geek = geek  

class MapSubclass(Map):

    # provides new signature for geek() but
    # does not break __init__()
    def geek(self, key, value):       
        for i in zip(keys, value):
            self.list.append(i)
```

篡改规则主要是为了避免事故，但是仍然可以访问或修改被认为是私有的变量。这在特殊情况下甚至很有用，例如在调试器中。

**_ 单前导下划线**

所以基本上在方法、函数或数据成员的开头加一条下划线意味着你不应该访问这个方法，因为它不是 API 的一部分。让我们看看这段代码:

## 计算机编程语言

```py
# Python code to illustrate
# how single underscore works
def _get_errors(self):
    if self._errors is None:
        self.full_clean()
    return self._errors

errors = property(_get_errors)
```

该片段取自 Django 源代码(django/forms/forms.py)。这表明错误是属性，也是 API 的一部分，但是方法 _get_errors 是“私有的”，所以不应该访问它。

**_ _ 双前导下划线**

两个下划线，在开始的时候，引起了很多混乱。这是语法问题，而不是惯例。双下划线会破坏类的属性名，以避免类之间的属性名冲突。例如:

## 计算机编程语言

```py
# Python code to illustrate how double
# underscore at the beginning works
class Geek:
    def _single_method(self):
        pass
    def __double_method(self): # for mangling
        pass
class Pyth(Geek):
    def __double_method(self): # for mangling
        pass
```

**_ _ 双前导双尾随下划线 __**

还有一种双前导和双尾随下划线的情况。我们在使用特殊变量或方法(称为“魔术方法”)时遵循这一点，例如 __len__、__init__。这些方法为名字提供了特殊的句法特征。例如，__file__ 表示 Python 文件的位置，__eq__ 在执行 a == b 表达式时执行。

**示例:**

## 计算机编程语言

```py
# Python code to illustrate double leading and
# double trailing underscore works
class Geek:

    # '__init__' for initializing, this is a
    # special method 
    def __init__(self, ab):
        self.ab = ab

    # custom special method. try not to use it
    def __custom__(self):
        pass
```

本文由**钦莫伊·蕾恩卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
我已经参考了 Python Docs、hackernoon.com 和 igorsobreira.com
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。