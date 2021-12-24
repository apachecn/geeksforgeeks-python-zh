# Python 中的 json.loads()

> 原文:[https://www.geeksforgeeks.org/json-loads-in-python/](https://www.geeksforgeeks.org/json-loads-in-python/)

**JSON** 代表 JavaScript 对象符号。这是一种用于存储和交换数据的轻量级数据交换格式。它是一种独立于语言的格式，非常容易理解，因为它本质上是自描述的。python 中有一个支持 JSON 数据的内置包，叫做`json`。JSON 中的数据表示为带引号的字符串，由括在花括号{}之间的键值映射组成。

## json.loads()

**json.loads()** 方法可用于解析有效的 json 字符串，并将其转换为 Python Dictionary。它主要用于将由 JSON 数据组成的本机字符串、字节或字节数组反序列化为 Python 字典。

> **语法:** json.loads
> 
> **参数:**它将包含 JSON 文档的字符串、字节或字节数组实例作为参数。
> 
> **返回:**返回一个 Python 对象。

**例 1:** 假设 JSON 字符串是这样的。

```
x = """{
    "Name": "Jennifer Smith",
    "Contact Number": 7867567898,
    "Email": "jen123@gmail.com",
    "Hobbies":["Reading", "Sketching", "Horse Riding"]
    }"""

```

为了读取该字符串的内容，需要执行以下实现:

```
import json

# JSON string:
# Multi-line string
x = """{
    "Name": "Jennifer Smith",
    "Contact Number": 7867567898,
    "Email": "jen123@gmail.com",
    "Hobbies":["Reading", "Sketching", "Horse Riding"]
    }"""

# parse x:
y = json.loads(x)

# the result is a Python dictionary:
print(y)
```

**输出:**

> { '爱好':['阅读'，'写生'，'骑马']，'姓名':'詹妮弗·史密斯'，'电子邮件':' jen123@gmail.com '，'联系电话':7867567898}

这里，使用返回字典的`json.loads()`方法解析字符串 x。

**例 2:**

```
import json 

# JSON string 
employee ='{"id":"09", "name": "Nitin", "department":"Finance"}'

# Convert string to Python dict 
employee_dict = json.loads(employee) 
print(employee_dict) 

print(employee_dict['name']) 
```

**输出:**

```
{'id': '09', 'department': 'Finance', 'name': 'Nitin'}
Nitin
```