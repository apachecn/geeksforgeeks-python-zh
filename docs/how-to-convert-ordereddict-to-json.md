# 如何将 Ordereddict 转换为 JSON？

> 原文:[https://www . geesforgeks . org/how-convert-ordereddct-to-JSON/](https://www.geeksforgeeks.org/how-to-convert-ordereddict-to-json/)

在本文中，我们将学习如何将嵌套的 OrderedDict 转换为 JSON？在此之前，我们必须了解一些概念:

*   JSON 的完整形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 JSON 的内置包支持 JSON。为了使用这个特性，我们在 Python 脚本中导入 JSON 包。
*   JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的一个值。它类似于 Python 中的字典。JSON 展示了一个类似于标准库封送和 pickle 模块的用户的应用编程接口，Python 本地支持 JSON 特性
*   OrderedDict 是一个字典子类，它记住键第一次插入的顺序。dict 和 OrderedDict()之间唯一的区别是:
*   OrderedDict 保留插入键的顺序。常规字典不跟踪插入顺序，迭代它会以任意顺序给出值。相比之下，项目的插入顺序由 OrderedDict 记住。

为了定义**ordereddct**，我们使用了 python 中的集合模块。

## 蟒蛇 3

```py
# import package
from collections import OrderedDict

# define OrderedDict
od1 = OrderedDict([('1','one'), 
                   ('2','two')])

# display dictionary
print(type(od1))
print(od1)
```

**输出:**

```py
<class 'collections.OrderedDict'>
OrderedDict([('1', 'one'), ('2', 'two')])
```

要将**ordereddct 转换为 JSON，**我们使用的是 **json.dumps()** 。

*   JSON 的完整形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 JSON 的内置包支持 JSON。为了使用这个特性，我们在 Python 脚本中导入 JSON 包。JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的值。它类似于 Python 中的字典。
*   *json.dumps()* 函数将 Python 对象转换为 json 字符串。

## 蟒蛇 3

```py
# import package
from collections import OrderedDict
import json

# define OrderedDict
od1 = OrderedDict([('1','one'), 
                   ('2','two')])

# check type i.e; OrderedDict
print(type(od1))

# convert to json
od1 = json.dumps(od1)

# check type i.e; str
print(type(od1))

# view value
print(od1)
```

**Output**

```py
<class 'collections.OrderedDict'>
<class 'str'>
{"1": "one", "2": "two"}
```

我们可以给出缩进值来显示字典模式。

## 蟒蛇 3

```py
# import package
from collections import OrderedDict
import json

# define OrderedDict
od1 = OrderedDict([('1', 'one'),
                   ('2', 'two')])

# check type i.e; OrderedDict
print(type(od1))

# convert to json
od1 = json.dumps(od1, indent=4)

# check type i.e; str
print(type(od1))

# view value
print(od1)
```

**输出:**

```py
<class 'collections.OrderedDict'>
<class 'str'>
{
    "1": "one",
    "2": "two"
}
```