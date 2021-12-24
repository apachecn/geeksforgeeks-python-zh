# Python JSON

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-JSON/

**JSON JavaScript 对象符号**是一种结构化数据的格式。它主要用于在浏览器和服务器之间存储和传输数据。Python 也通过一个名为 json 的内置包支持 JSON。这个包提供了使用 JSON 对象的所有必要工具，包括解析、序列化、反序列化等等。让我们看一个简单的例子，其中我们将 JSON 对象转换为 Python 对象，反之亦然。

**示例:**

## 蟒蛇 3

```
import json

# JSON string
employee = '{"id":"09", "name": "Nitin", "department":"Finance"}'

# Convert string to Python dict
employee_dict = json.loads(employee)
print(employee_dict)
print(type(employee_dict))
print("\n")

# Convert Python dict to JSON
json_object = json.dumps(employee_dict, indent=4)
print(json_object)
print(type(json_object))
```

**输出:**

```
 {'id': '09', 'name': 'Nitin', 'department': 'Finance'}
<class 'dict'>

{
    "id": "09",
    "name": "Nitin",
    "department": "Finance"
}
<class 'str'>
```

本 JSON 教程将帮助您从基础到高级学习使用 Python 处理 JSON，例如解析 JSON、读写 JSON 文件、使用大量 JSON 程序序列化和反序列化 JSON。

![](img/700b8566c9d5d2ee2bcb122f4fb2e996.png)

## 介绍

*   [什么是 JSON？](https://www.geeksforgeeks.org/javascript-json/)
*   [JSON 中的数据类型](https://www.geeksforgeeks.org/json-data-types/)
*   [使用 Python 中的 JSON 数据](https://www.geeksforgeeks.org/working-with-json-data-in-python/)
*   [使用 Python 读取、写入和解析 JSON】](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/)

## 读写 JSON

*   [用 Python 将 JSON 读写到文件中](https://www.geeksforgeeks.org/reading-and-writing-json-to-a-file-in-python/)
*   [使用 Python 读取 JSON 文件](https://www.geeksforgeeks.org/read-json-file-using-python/)
*   [使用 Python 追加到 JSON 文件中](https://www.geeksforgeeks.org/append-to-json-file-using-python/)

## 解析 JSON

*   [如何将数据从 JSON 解析成 Python？](https://www.geeksforgeeks.org/how-to-parse-data-from-json-into-python/)
*   [如何将 Python 字典转换为 JSON？](https://www.geeksforgeeks.org/how-to-convert-python-dictionary-to-json/)
*   [Python–将 JSON 转换为字符串](https://www.geeksforgeeks.org/python-convert-json-to-string/)
*   [将字符串转换为 json 对象的方法](https://www.geeksforgeeks.org/python-ways-to-convert-string-to-json-object/)
*   [将 JSON 数据转换成自定义 Python 对象](https://www.geeksforgeeks.org/convert-json-data-into-a-custom-python-object/)

## 序列化和反序列化 JSON

*   [在 Python 中序列化 JSON](https://www.geeksforgeeks.org/serializing-json-data-in-python/)
*   [Python 中的 json.dump()](https://www.geeksforgeeks.org/json-dump-in-python/)
*   [Python 中的 json.dumps()](https://www.geeksforgeeks.org/json-dumps-in-python/)
*   [Python–JSON . dump()和 JSON . dump()](https://www.geeksforgeeks.org/python-difference-between-json-dump-and-json-dumps/)的区别
*   [在 Python 中将 JSON 反序列化为对象](https://www.geeksforgeeks.org/deserialize-json-to-object-in-python/)
*   [Python 中的 json.load()](https://www.geeksforgeeks.org/json-load-in-python/)
*   [Python 中的 json.loads()](https://www.geeksforgeeks.org/json-loads-in-python/)
*   [JSON . load()和 json.loads()](https://www.geeksforgeeks.org/python-difference-between-json-load-and-json-loads/) 的区别
*   [Python-JSON 中自定义对象的编码和解码](https://www.geeksforgeeks.org/encoding-and-decoding-custom-objects-in-python-json/)
*   [在 Python 中序列化和反序列化复杂的 JSON](https://www.geeksforgeeks.org/serialize-and-deserialize-complex-json-in-python/)

## JSON 之间的转换

*   [Python–JSON 转 XML](https://www.geeksforgeeks.org/python-json-to-xml/)
*   [Python–XML 到 JSON](https://www.geeksforgeeks.org/python-xml-to-json/)
*   [使用 Python 将 CSV 转换为 JSON】](https://www.geeksforgeeks.org/convert-csv-to-json-using-python/)
*   [将多个 JSON 文件转换为 CSV Python](https://www.geeksforgeeks.org/convert-multiple-json-files-to-csv-python/)
*   [将文本文件转换为 Python 中的 JSON](https://www.geeksforgeeks.org/convert-text-file-to-json-in-python/)
*   [用 Python 将文本、JSON 和 CSV 保存到文件中](https://www.geeksforgeeks.org/saving-text-json-and-csv-to-a-file-in-python/)

## 更多操作 JSON

*   [Python 中的 JSON 格式](https://www.geeksforgeeks.org/json-formatting-python/)
*   [Python 中的漂亮打印 JSON](https://www.geeksforgeeks.org/pretty-print-json-in-python/)
*   [在 Python 中展平 JSON 对象](https://www.geeksforgeeks.org/flattening-json-objects-in-python/)
*   [检查字符串是否有效](https://www.geeksforgeeks.org/python-check-whether-a-string-is-valid-json-or-not/)
*   [按值排序 JSON](https://www.geeksforgeeks.org/python-sort-json-by-value/)