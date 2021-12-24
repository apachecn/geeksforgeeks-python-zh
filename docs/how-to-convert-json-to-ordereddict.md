# 如何将 JSON 转换为 Ordereddict？

> 原文:[https://www . geeksforgeeks . org/how-convert-JSON-to-ordereddct/](https://www.geeksforgeeks.org/how-to-convert-json-to-ordereddict/)

JSON 的完整形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 *json* 的内置包支持 JSON。为了使用这个特性，我们用 Python 脚本导入 *json* 包。JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的一个值。它类似于 Python 中的字典。

一个 *OrderedDict* 是一个字典子类，它会记住首次插入键的顺序。 *dict()* 和*ordereddct()*的唯一区别在于:*ordereddct*保留了按键插入的顺序。常规的*字典*不跟踪插入顺序，迭代它以任意顺序给出值。

在本文中，我们将讨论将 *JSON* 转换为*ordereddct*的各种方法。

**方法#1**

通过将*对象 _pairs_hook* 参数指定给 *JSONDecoder。*

## 计算机编程语言

```
# import required modules
import json
from collections import OrderedDict

# assign json file
jsonFile = '{"Geeks":1, "for": 2, "geeks":3}'
print(jsonFile)

# convert to Ordereddict
data = json.JSONDecoder(object_pairs_hook=OrderedDict).decode(jsonFile)
print(data)
```

**输出:**

```
{"Geeks":1, "for": 2, "geeks":3}
OrderedDict([(u'Geeks', 1), (u'for', 2), (u'geeks', 3)])
```

**方法 2**

通过将 JSON 数据作为参数传递给[json.loads()](https://www.geeksforgeeks.org/json-load-in-python/) 。

## 计算机编程语言

```
# import required modules
import json
from collections import OrderedDict

# assign json file
jsonFile = '{"Geeks":1, "for": 2, "geeks":3}'
print(jsonFile)

# convert to Ordereddict
data = json.loads(jsonFile, 
                  object_pairs_hook=OrderedDict)
print(data)
```

**输出:**

```
{"Geeks":1, "for": 2, "geeks":3}
OrderedDict([(u'Geeks', 1), (u'for', 2), (u'geeks', 3)])
```