# 带 Python 的 JSON】

> 原文:[https://www.geeksforgeeks.org/json-with-python/](https://www.geeksforgeeks.org/json-with-python/)

**JSON(JavaScript Object notification)**是一个主要用于存储和传输数据的文件，主要用于服务器和 web 应用程序之间。它通常用于表示结构化数据。在本文中，我们将讨论如何使用 Python 处理 JSON 数据。Python 提供了一个名为 **json** 的模块，该模块附带了 Python 的标准内置实用程序。

**注意:**在 Python 中，JSON 数据通常表示为字符串。

## 导入模块

要使用 Python 中的任何模块，总是需要导入该模块。我们可以使用[导入](https://www.geeksforgeeks.org/import-module-python/)语句导入 json 模块。

**示例:**导入 JSON 模块

## 蟒蛇 3

```py
# importing json module
import json
```

## 解析 JSON–从 JSON 转换为 Python

json 模块的 [load()](https://www.geeksforgeeks.org/json-load-in-python/) 和[load()](https://www.geeksforgeeks.org/json-loads-in-python/)功能使得解析 JSON 对象变得更加容易。

### 解析 JSON 字符串

[loads()](https://www.geeksforgeeks.org/json-loads-in-python/) 方法用于解析 Python 中的 JSON 字符串，结果将是一个 Python 字典。

**语法:**

```py
json.loads(json_string)
```

**示例:**将 JSON 转换为字典

## 蟒蛇 3

```py
# Python program to convert JSON to Dict

import json

# JSON string
employee ='{"name": "Nitin", "department":"Finance",\
"company":"GFG"}'

# Convert string to Python dict
employee_dict = json.loads(employee)
print("Data after conversion")
print(employee_dict)
print(employee_dict['department'])

print("\nType of data")
print(type(employee_dict))
```

**Output**

```py
Data after conversion
{'name': 'Nitin', 'department': 'Finance', 'company': 'GFG'}
Finance

Type of data
<class 'dict'>
```