# Python 中的数据类|集合 2(装饰器参数)

> 原文:[https://www . geesforgeks . org/data-class-in-python-set-2-decorator-parameters/](https://www.geeksforgeeks.org/data-classes-in-python-set-2-decorator-parameters/)

前提条件:[Python 中的数据类|集合 1](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/)

在这篇文章中，我们将讨论如何修改`**dataclass**` 模块虚拟为我们制作的默认构造函数。

**`dataclass()`装饰师–**

> @ dataclass . dataclass(*，init=True，repr=True，eq=True，order=False，unsafe_hash=False，frozen = False)

通过改变这些参数的值，我们可以修改我们的数据类的默认构造函数的行为和功能。

**init:** 此参数指定是否应该有默认构造函数。

```
True (default): There will be a default Constructor.
False         : There won't be a default Constructor.
```

```
from dataclasses import dataclass

@dataclass(init = False)
class GfgArticle():

    title: str
    author: str
    language: str
    upvotes: int

# A DataClass object
article = GfgArticle("DataClasses",
                     "vibhu4agarwal",
                     "Python", 0)
```

```
TypeError: object() takes no parameters

```

**repr :** 该参数指定了 [__repr__()](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-2-data-hiding-and-object-printing/) 函数的行为。**假**值对应内存中对象的哈希值表示。**真**值对应于对象的数据类表示。

```
from dataclasses import dataclass

@dataclass(repr = False)
class GfgArticle():

    title: str
    author: str
    language: str
    upvotes: int

# A DataClass object
article = GfgArticle("DataClasses",
                     "vibhu4agarwal",
                     "Python", 0)
print(article)
```

**输出:**

```
__main__.GfgArticle object at 0x7f391b7ddbe0
```

**eq :** 此参数用于指定使用 **==** 或**比较两个数据类是否相等时进行的比较操作！=** 操作员。 *eq* 采用布尔值。

```
from dataclasses import dataclass

@dataclass(repr = False, eq = False)
class GfgArticle():

    title: str
    author: str
    language: str
    upvotes: int

# Two DataClass objects
dClassArticle1 = GfgArticle("DataClasses",
                            "vibhu4agarwal",
                            "Python", 0)

dClassArticle2 = GfgArticle("DataClasses",
                            "vibhu4agarwal",
                            "Python", 0)

equal = dClassArticle1 == dClassArticle2
print('Classes Equal:', equal)
```

**输出:**

```
__main__.GfgArticle object at 0x7ff501c63c18
__main__.GfgArticle object at 0x7ff501c63ba8
Classes Equal: False

```

当 **eq=False** 时，两个对象使用基于其在内存中位置的散列进行比较，就像两个普通对象一样。由于两个对象具有不同的哈希表示，因此它们的相等性返回 False。

**顺序:**两个 DataClasses 之间的比较不仅仅限于相等，在参数中设置**顺序=True** 时，还支持**>****>=****<**和 **< =** 运算符。
对象之间的比较是基于它们对应属性之间的比较，从第一个开始逐一进行。

```
from dataclasses import dataclass 

@dataclass(order = True)
class A():
    var1: int
    var2: str
    var3: float

obj1 = A(1, "GeeksForGeeks", 7.0)
obj2 = A(2, "GeeksForGeeks", 7.0)
obj3 = A(1, "GfG", 7.0)
obj4 = A(1, "GeeksForGeeks", 8.0)

print(obj1 >  obj2)
print(obj1 <  obj3)
print(obj1 >= obj4)
```

**输出:**

```
False
True
False

```

**冻结:**这将 DataClass 中的所有变量设置为一次性可初始化的，一旦初始化，就不能为其重新分配新值。C++用户可以将其与 **const** 联系起来，Java 用户可以将其与 **final** 关键字联系起来。

```
from dataclasses import dataclass 

@dataclass(frozen = True)
class GfgArticle():

    title: str
    author: str
    language: str
    upvotes: int

dClassArticle = GfgArticle("DataClasses",
                           "vibhu4agarwal",
                           "Python", 0)
print(dClassArticle)

dClassArticle.upvotes = 100
print(dClassArticle)
```

> GfgArticle(title='DataClasses '，作者='vibhu4agarwal '，语言='Python '，up loats = 0)
> 回溯(最近一次调用最后一次):
> 文件“dClass.py”，第 16 行，在<模块>中
> dclass article . up loats = 100
> 文件“<字符串>”，第 3 行，在 __setattr__
> dataclasses 中。FrozenInstanceError:无法分配给字段“up loats”

**unsafe_hash :** 一般来说，python 中的可变对象是*不可变的*。这意味着不能使用 Python 的[哈希()](https://www.geeksforgeeks.org/python-hash-method/)函数生成它们的哈希。
由于包括数据类对象的值在内的任何类对象都可以改变，因此它们是可变的。因此，他们不应该能够产生任何哈希值。

```
from dataclasses import dataclass 

@dataclass
class GfgArticle():

    title: str
    author: str
    language: str
    upvotes: int

dClassArticle = GfgArticle("DataClasses",
                           "vibhu4agarwal",
                           "Python", 0)
print(dClassArticle)
print(hash(dClassArticle))
```

> GfgArticle(title='DataClasses '，author='vibhu4agarwal '，language='Python '，up loats = 0)
> 回溯(最近一次调用最后一次):
> 文件“dClass.py”，第 15 行，在<模块>
> 打印(hash(dclassagarticle))
> 类型错误:不可清除类型:“GfgArticle”

然而**冻结=真**设置变量一次性可初始化，因此使对象不可变。这可以安全地为数据类对象生成一个哈希。

```
from dataclasses import dataclass 

@dataclass(frozen = True)
class GfgArticle():

    title: str
    author: str
    language: str
    upvotes: int

dClassArticle = GfgArticle("DataClasses",
                           "vibhu4agarwal",
                           "Python", 0)
print(dClassArticle)
print(hash(dClassArticle))
```

**输出:**

> GfgArticle(title='DataClasses '，作者='vibhu4agarwal '，语言='Python '，up loats = 0)
> 9111021502060859577

*unsafe_hash* 强制一个仍然可变的 DataClass 生成一个 hash。

当逻辑上，我们知道一旦初始化，我们就不会改变 Dataclass 属性值时，这种情况就开始使用了。但归根结底是*能不能改的问题？*或者换句话说，*DataClass 是不是没有冻结？*在使用 *unsafe_hash* 的时候，如果 DataClass 没有被冻结，那么 DataClass 会生成一个 *unsafe* hash，假设这个类被冻结了，那么程序员就要非常小心地进一步使用这个。

```
from dataclasses import dataclass 

@dataclass(unsafe_hash = True)
class GfgArticle():

    title: str
    author: str
    language: str
    upvotes: int

dClassArticle = GfgArticle("DataClasses",
                           "vibhu4agarwal",
                           "Python", 0)
print(dClassArticle)
print(hash(dClassArticle))
```

**输出:**

> GfgArticle(title='DataClasses '，作者='vibhu4agarwal '，语言='Python '，up vots = 0)
> 8924105619418522237