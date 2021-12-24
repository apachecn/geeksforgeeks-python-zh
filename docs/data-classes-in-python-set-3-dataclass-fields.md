# Python 中的数据类|集合 3(数据类字段)

> 原文:[https://www . geesforgeks . org/data-class-in-python-set-3-data class-field/](https://www.geeksforgeeks.org/data-classes-in-python-set-3-dataclass-fields/)

先决条件:[Python 中的数据类集 1](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/) | [集 2](https://www.geeksforgeeks.org/data-classes-in-python-set-2-decorator-parameters/)

在这篇文章中，我们将讨论如何修改 DataClass 对象属性的某些属性，而不需要使用`**field**`函数为其显式编写代码。

**`field()`功能–**

> data class . field(*，default=MISSING，default_factory=MISSING，repr=True，hash=None，init=True，compare=True，metadata=None)

`MISSING`值是用于检测是否提供了`default`和`default_factory`参数的监控对象。使用此哨兵是因为`None`是`default`的有效值。没有代码应该直接使用`MISSING`值。

**默认值:**如果在对象创建过程中没有提供值，该参数指定属性的默认值。与函数中的参数类似，具有默认值的*字段必须位于任何没有默认值的字段之后。*
还有一种提供默认值的替代方法——就像您使用 **=** 运算符对普通变量所做的那样。(下面代码中的第 9 行)

```
from dataclasses import dataclass, field

@dataclass
class GfgArticle:

    title: str
    author: str
    language: str = field(default ='Python3')
    upvotes: int = 0

# A DataClass object
article = GfgArticle("DataClass", "vibhu4agarwal")
print(article)
```

**输出:**

```
GfgArticle(title='DataClass', author='vibhu4agarwal', language='Python3', upvotes=0)

```

**default_factory :** 如果提供，它必须是一个*零参数*可调用函数，当该字段需要默认值时将调用该函数。
可调用的返回值将被设置为对象创建中属性的默认值。
要么为默认工厂提供一个可调用的，要么为属性提供一个默认值。同时指定**默认**和**默认 _ 工厂**是错误的。

```
from dataclasses import dataclass, field
from random import choice

def get_default_language():
    languages = ['Python3', 'Java', "CPP"]
    return choice(languages)

@dataclass
class GfgArticle:

    title: str
    author: str
    language: str = field(default_factory = get_default_language)
    upvotes: int = 0

# A DataClass object
article = GfgArticle("DataClass", "vibhu4agarwal")
print(article)
```

上面的代码将 Python3、Java 或 CPP 中的一个作为创建数据类对象时的语言默认值。

**init** 、 **repr** 和 **hash** 参数类似于[上一篇文章](https://www.geeksforgeeks.org/data-classes-in-python-set-2-decorator-parameters/)中讨论的 dataclass 函数中的参数。**比较**参数可以与**顺序**相关，就像在 dataclass 函数中一样。不同之处在于它们只适用于特定的属性，而不是装饰器下的数据类中的所有属性。

**初始化:**如果为真(默认值)，该字段将作为参数包含在生成的 __init__()方法中。当`init`设置为`False`时，应提供一种设置默认值的方法。

**repr :** 如果为真(默认值)，则该字段包含在由生成的 __repr__()方法返回的字符串中。

**比较:**如果为真(默认值)，则此字段包含在生成的等式和比较方法中(__eq__()，__gt__()，等)。

```
from dataclasses import dataclass, field

@dataclass
class GfgArticle:

    title: str = field(compare = False)
    author: str = field(repr = False)
    language: str = field(default ='Python3')
    upvotes: int = field(init = False, default = 0)

# DataClass objects
# Note the difference in their title value
article1 = GfgArticle("DataClass", "vibhu4agarwal")
article2 = GfgArticle("Python Packaging", "vibhu4agarwal")

print(article1)
print(article1.author)
print(article1 == article2)
```

**输出:**

```
GfgArticle(title='DataClass', language='Python3', upvotes=0)
vibhu4agarwal
True

```

**哈希:**这可以是`bool`或`None`。如果为真，则此字段包含在生成的 __hash__()方法中。如果`None`(默认值)，使用`compare`的值:这通常是预期的行为。
如果一个字段用于比较，则应该在散列中考虑它。不鼓励将该值设置为除`None`以外的任何值。

**元数据:**这通常是一个字典，表示各种信息及其数据的键值对。
这个特殊的属性似乎并不是在大多数时候都在使用，但是如果您的数据类在开发过程中确实在某个地方使用，并且当第三方的工具或软件集成到项目中时，该属性的数据被第三方使用或访问，这一点很重要。
在脚本中，可以通过查询对象的 **__dataclass_fields__** 变量来访问它的值。

```
from dataclasses import dataclass, field

@dataclass
class GfgArticle:

    title: str = field(compare = False)
    author: str = field(metadata ={'data': 'Profile Handle'})
    language: str = field(default ='Python3')
    upvotes: int = field(init = False, default = 0)

# A DataClass object
article = GfgArticle("DataClass", "vibhu4agarwal")
print(article)
print(article.__dataclass_fields__['author'].metadata)
```

**输出:**

```
GfgArticle(title='DataClass', author='vibhu4agarwal', language='Python3', upvotes=0)
{'data': 'Profile Handle'}

```