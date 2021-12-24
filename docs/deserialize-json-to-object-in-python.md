# 在 Python 中将 JSON 反序列化为对象

> 原文:[https://www . geesforgeks . org/deserize-JSON-to-object-in-python/](https://www.geeksforgeeks.org/deserialize-json-to-object-in-python/)

让我们看看如何将 JSON 文档反序列化为 Python 对象。反序列化是将 JSON 格式的数据解码为本机数据类型的过程。在 python 中，反序列化将 JSON 数据解码成字典(Python 中的数据类型)。
我们将使用 **json** 模块的这些方法来执行此任务:

*   [**loads()**](https://www.geeksforgeeks.org/json-loads-in-python/) :将 JSON 文档反序列化为 Python 对象。
*   [**load()**](https://www.geeksforgeeks.org/json-load-in-python/) :将 JSON 格式的流(支持从文件读取)反序列化为 Python 对象。

**示例 1 :** 使用 loads()函数。

## 蟒蛇 3

```
# importing the module
import json

# creating the JSON data as a string
data = '{"Name" : "Romy", "Gender" : "Female"}'

print("Datatype before deserialization : "
      + str(type(data)))

# deserializing the data
data = json.loads(data)

print("Datatype after deserialization : "
      + str(type(data)))
```

**输出:**

```
Datatype before deserialization : 
Datatype after deserialization : 
```

**示例 2 :** 使用 load()函数。我们必须反序列化一个名为 file.json.
的文件

![](img/557337e20dd71e7741f54d9f22d71f88.png)

## 蟒蛇 3

```
# importing the module
import json

# opening the JSON file
data = open('file.json',)

print("Datatype before deserialization : "
      + str(type(data)))

# deserializing the data
data = json.load(data)

print("Datatype after deserialization : "
      + str(type(data)))
```

**输出:**

```
Datatype before deserialization : 
Datatype after deserialization : 
```