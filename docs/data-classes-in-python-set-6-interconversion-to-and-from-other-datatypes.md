# Python 中的数据类|集合 6(与其他数据类型的相互转换)

> 原文:[https://www . geesforgeks . org/data-class-in-python-set-6-相互转换到其他数据类型/](https://www.geeksforgeeks.org/data-classes-in-python-set-6-interconversion-to-and-from-other-datatypes/)

前提条件:[Python 中的数据类|集合 5](https://www.geeksforgeeks.org/data-classes-in-python-set-5-post-init/)

在数据类系列的最后一篇文章中，我们将讨论如何将数据类对象的值获取到字典或元组对中，以及如何以不同的方式创建数据类——从值开始，而不是直接定义它。

**`asdict()`功能–**

```
dataclasses.asdict(instance, *, dict_factory=dict)

```

通过使用这个函数，可以简单地获得字典形式的属性到值对的映射，将 DataClass 对象传递给函数的`instance`参数。

**`astuple()`功能–**

```
dataclasses.astuple(instance, *, tuple_factory=tuple)

```

与 asdict 类似，通过将 dataclass 对象传递给函数的`instance`参数，可以简单地使用这个函数获得元组形式的 DataClass 属性的有序值。

```
from dataclasses import dataclass, field, 
from dataclasses import asdict, astuple

@dataclass
class GfgArticle:

    title : str
    language: str
    author: str
    upvotes: int = field(default = 0)

dClassObj = GfgArticle("DataClass",
                       "Python3",
                       "vibhu4agarwal")

dictArticle = asdict(dClassObj)
tupleArticle = astuple(dClassObj)

print(dictArticle)
print(tupleArticle)
```

**输出:**

> {'title': 'DataClass '，' language': 'Python3 '，' author': 'vibhu4agarwal '，' uploats ':0 }
> (' DataClass '，' Python3 '，' vibhu4agarwal '，0)

**`make_dataclass()`功能–**

> data class . make _ dataclass(cls _ name，fields，* base =()，namespace=None，init=True，repr=True，eq=True，order=False，unsafe_hash=False，frozen = False)

该函数通过以字符串形式传递名称和各种属性，帮助您创建数据类*(不是数据类对象的对象)*。当您想要动态创建一个属性名称可能依赖于某些值的数据类时，这非常有用，然后您可以通过`str`变量传递它们的名称。
在上述功能中，如果只提供 **`name`** ，则类型使用`typing.Any`。
**`init`**、 **`repr`** 、 **`eq`** 、 **`order`** 、 **`unsafe_hash`** 、 **`frozen`** 的值与 [dataclass()](https://www.geeksforgeeks.org/data-classes-in-python-set-2-decorator-parameters/) 中的值含义相同。

```
from dataclasses import make_dataclass, field

GfgArticle = make_dataclass(
    'GfgArticle',
    [
        ('title', str),
        ('language', str),
        ('author', str),
        ('upvotes', int, field(default = 0))
    ]
)

dClassObj = GfgArticle("DataClass",
                       "Python3",
                       "vibhu4agarwal")
print(dClassObj)
```

**输出:**

> GfgArticle(title='DataClass '，language='Python3 '，author='vibhu4agarwal '，up loats = 0)

由于这是最后一篇帖子，这里有一个奖励功能。

**`is_dataclass()`功能–**

```
dataclasses.is_dataclass(class_or_instance)

```

如果参数为`dataclass`或数据类对象，则该函数返回`True`，否则返回`False`。

```
from dataclasses import is_dataclass

print(is_dataclass(dictArticle))
print(is_dataclass(tupleArticle))

print(is_dataclass(dClassObj))
print(is_dataclass(GfgArticle))

print(is_dataclass(dClassObj) and not isinstance(dClassObj, type))
print(is_dataclass(GfgArticle) and not isinstance(GfgArticle, type))
```

**输出:**

```
False
False
True
True
True
False

```