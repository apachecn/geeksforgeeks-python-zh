# 如何将 Python 字典转换为 JSON？

> 原文:[https://www . geesforgeks . org/how-convert-python-dictionary-to-JSON/](https://www.geeksforgeeks.org/how-to-convert-python-dictionary-to-json/)

JSON 代表 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 json 的内置包支持 JSON。为了使用这个特性，我们在 Python 脚本中导入 JSON 包。JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的一个值。它类似于 Python 中的字典。
**注:**更多信息请参考[使用 Python 读取、写入和解析 JSON](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/)

**使用的功能:**

*   json.dumps()

*   json.dump()

> **语法:** json.dumps(dict，indent)
> **参数:**
> 
> *   **字典–**应该转换为 JSON 对象的字典的名称。
>     
> *   **缩进–**定义缩进的单位数
>     
> 
> **语法:** json.dump(dict，file_pointer)
> **参数:**
> 
> *   **字典–**应该转换为 JSON 对象的字典的名称。
>     
> *   **文件指针–**以写入或追加模式打开的文件的指针。

**例 1:**

## 蟒蛇 3

```
import json 

# Data to be written 
dictionary ={ 
  "id": "04", 
  "name": "sunil", 
  "department": "HR"
} 

# Serializing json  
json_object = json.dumps(dictionary, indent = 4) 
print(json_object)
```

**Output**

```
{
    "id": "04",
    "name": "sunil",
    "department": "HR"
}
```

**输出:**

```
{
    "department": "HR",
    "id": "04",
    "name": "sunil"
}
```

**例 2:**

## 蟒蛇 3

```
import json

# Data to be written
dictionary ={
    "name" : "sathiyajith",
    "rollno" : 56,
    "cgpa" : 8.6,
    "phonenumber" : "9976770500"
}

with open("sample.json", "w") as outfile:
    json.dump(dictionary, outfile)
```

**输出:**

![python-json-write-to-file-1](img/71953d4ada0093ff1737f8574f1b9646.png)