# Python 中的数据类|集合 5(初始化后)

> 原文:[https://www . geesforgeks . org/data-class-in-python-set-5-post-init/](https://www.geeksforgeeks.org/data-classes-in-python-set-5-post-init/)

前提条件:[Python 中的数据类|集合 4](https://www.geeksforgeeks.org/data-classes-in-python-set-4-inheritance/)

在这篇文章中，我们将讨论如何在对象创建过程中修改一些属性的值，而不用使用初始化后处理在`__init__()`中编码。

**`__post_init__()` :** 该函数在生成时，由内置的 __init__()在初始化 DataClass 的所有属性后调用。基本上，数据类的对象创建以`__init__()`(构造函数调用)开始，以`__post__init__()`(初始化后处理)结束。

**使用–**
当某些属性依赖于在`__init__()`中传递的参数，但不直接从这些参数中获取它们的值时，该功能非常方便。也就是说，它们在对构造函数中接收到的参数子集执行一些操作后获得它们的值。

继续我们在本系列文章中看到的相同示例，假设有一个名为 **`author_name`** 的属性，该属性从配置文件句柄获取其值，以在定义的字典 **`name`** 中进行名称映射。
所以 **`author_name`** 是依赖于 **`author`** 属性接收到的轮廓柄，所以使用`__post_init__()`应该是这种情况下的理想选择。

```
from dataclasses import dataclass, field

name = {'vibhu4agarwal': 'Vibhu Agarwal'}

@dataclass
class GfgArticle:

    title : str
    language: str
    author: str
    author_name: str = field(init = False)
    upvotes: int = 0

    def __post_init__(self):
        self.author_name = name[self.author]

dClassObj = GfgArticle("DataClass", "Python3", "vibhu4agarwal")
print(dClassObj)
```

**输出:**

> GfgArticle(title='DataClass '，language='Python3 '，author = ' vibhu4agarwal '，author _ name = ' Vibhu Agarwal '，up loats = 0)

**能不能成为一个替代？**
不是，因为 **`default_factory`** 接受零参数函数或者是可调用的，所以它不能接收任何参数，并且在对其执行一些操作后返回值。