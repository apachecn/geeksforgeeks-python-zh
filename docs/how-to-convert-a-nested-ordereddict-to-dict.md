# 如何将嵌套的 OrderedDict 转换为 Dict？

> 原文:[https://www . geesforgeks . org/how-convert-a-nested-ordereddct-to-dict/](https://www.geeksforgeeks.org/how-to-convert-a-nested-ordereddict-to-dict/)

在本文中，我们将讨论如何将嵌套的*ordereddct*转换为 *dict* ？在此之前，我们必须了解一些概念:

*   [**Python 中的 Dictionary**](https://www.geeksforgeeks.org/python-dictionary/) 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存的是键:值对。字典中提供了键值，以使其更加优化。
*   一个[**ordereddct**](https://www.geeksforgeeks.org/ordereddict-in-python/)是一个字典子类，它记住了首次插入键的顺序。
*   *dict()* 和*ordereddct()*唯一的区别是:*ordereddct***保留了插入按键的顺序**。一个常规字典不会跟踪插入顺序，迭代它会以任意顺序给出值。相比之下，插入项目的顺序由 *OrderedDict* 记忆。

为了定义嵌套的**ordereddct**，我们使用 python 中的*集合*模块。

## 蟒蛇 3

```py
#import package
from collections import OrderedDict

# define OrderedDict
od1 = OrderedDict([('1', 'one'), ('2', 'two')])
print(type(od1))
print(od1)

# define nested OrderedDict
od2 = OrderedDict([('1', 'one'),
                   ('2', OrderedDict([('-2',
                                       '-ive'),
                                      ('+2',
                                       '+ive')]))])
print(type(od2))
print(od2)
```

**输出:**

> <class></class>
> 
> ordereddct([(' 1 '，'一'，(' 2 '，'二')])
> 
> <class></class>
> 
> OrderedDict([('1 '，' one ')，(' 2 '，OrderedDict([('-2 '，'-ive ')，('+2 '，'+ive ')])])

我们可以在一行内将**ordereddct**转换为 **dict** ，但这仅适用于简单的**ordereddct**、**、**而不适用于**嵌套 ordereddct。**

## 蟒蛇 3

```py
# import package
from collections import OrderedDict

# define OrderedDict
od1 = OrderedDict([('1', 'one'), ('2', 'two')])

# convert to dict
od1 = dict(od1)

# display dictionary
print(type(od1))
print(od1)
```

**输出:**

```py
<class 'dict'>
{'1': 'one', '2': 'two'}
```

因此，要将嵌套的**ordereddct**转换为 **dict，**我们使用 **json.loads()** 和 **json.dumps()** 方法。

*   JSON 的完整形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 JSON 的内置包支持 JSON。为了使用这个特性，我们在 Python 脚本中导入 JSON 包。JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的值。它类似于 Python 中的字典。
*   可以使用 *json.loads()* 方法解析有效的 json 字符串，并将其转换为 Python 字典。它主要用于将由 JSON 数据组成的本机字符串、字节或字节数组反序列化为 Python 字典。
*   函数的作用是:将 Python 对象转换成 json 字符串。

## 蟒蛇 3

```py
# import package
from collections import OrderedDict
import json

# define nested OrderedDict
od2 = OrderedDict([('1', 'one'),
                   ('2', OrderedDict([('-2',
                                       '-ive'),
                                      ('+2',
                                       '+ive')]))])
# convert to dict
od2 = json.loads(json.dumps(od2))

# display deictionary
print(type(od2))
print(od2)
```

**输出:**

```py
<class 'dict'>
{'1': 'one', '2': {'-2': '-ive', '+2': '+ive'}}
```