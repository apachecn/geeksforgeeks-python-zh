# 将 JSON 数据转换成自定义 Python 对象

> 原文:[https://www . geesforgeks . org/convert-JSON-data-to-a-custom-python-object/](https://www.geeksforgeeks.org/convert-json-data-into-a-custom-python-object/)

让我们看看如何在 Python 中将 JSON 数据转换成自定义对象。将 JSON 数据转换为自定义 python 对象也称为**解码**或**反序列化** JSON 数据。要解码 JSON 数据，我们可以使用 **json.loads()** 、 [**json.load()**](https://www.geeksforgeeks.org/json-load-in-python/) 方法和 **object_hook** 参数。使用 object_hook 参数是为了当我们执行 json.loads()时，将使用 object_hook 的返回值而不是默认的 dict 值。我们也可以使用这个实现自定义解码器。
**例 1 :**

## 蟒蛇 3

```py
# importing the module
import json
from collections import namedtuple

# creating the data
data = '{"name" : "Geek", "id" : 1, "location" : "Mumbai"}'

# making the object
x = json.loads(data, object_hook =
               lambda d : namedtuple('X', d.keys())
               (*d.values()))

# accessing the JSON data as an object
print(x.name, x.id, x.location)
```

**输出:**

![](img/87d3a236224f7d563c677e166831c4a6.png)

正如我们在上面的例子中所看到的，名为的**是集合模块下的一个类。它包含映射到某些值的键。在这种情况下，我们可以使用键和索引来访问元素。我们还可以创建一个**自定义解码器**函数，在这个函数中，我们可以将 dict 转换为自定义 Python 类型，并将该值传递给 object_hook 参数，如下一个示例所示。
**例 2 :****

## 蟒蛇 3

```py
# importing the module
import json
from collections import namedtuple

# customDecoder function
def customDecoder(geekDict):
    return namedtuple('X', geekDict.keys())(*geekDict.values())

# creating the data
geekJsonData = '{"name" : "GeekCustomDecoder", "id" : 2, "location" : "Pune"}'

# creating the object
x = json.loads(geekJsonData, object_hook = customDecoder)

# accessing the JSON data as an object
print(x.name, x.id, x.location)
```

**输出:**

![](img/4b935ece5b40f70749021de2b59e04f6.png)

我们也可以使用类型模块中的 **SimpleNamespace** 类作为 JSON 对象的容器。简单命名空间解决方案相对于命名空间双解决方案的优势:-

1.  它更快，因为它没有为每个对象创建一个类。
2.  它更短更简单。

**例 3 :**

## 蟒蛇 3

```py
# importing the module
import json
try:
    from types import SimpleNamespace as Namespace
except ImportError:
    from argparse import Namespace

# creating the data
data = '{"name" : "GeekNamespace", "id" : 3, "location" : "Bangalore"}'

# creating the object
x = json.loads(data, object_hook = lambda d : Namespace(**d))

# accessing the JSON data as an object
print(x.name, x.id, x.location)
```

**输出:**

![](img/29122f24509dafc60f44a58d124ce4b8.png)