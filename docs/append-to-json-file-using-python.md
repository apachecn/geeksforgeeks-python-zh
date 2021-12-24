# 使用 Python 追加到 JSON 文件中

> 原文:[https://www . geesforgeks . org/append-to-JSON-file-use-python/](https://www.geeksforgeeks.org/append-to-json-file-using-python/)

JSON 的完整形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 JSON 的内置包支持 JSON。为了使用这个特性，我们在 Python 脚本中导入 JSON 包。JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的值。

### **使用的功能:**

*   **json.loads():** json.loads()函数存在于 python 内置的‘JSON’模块中。该函数用于解析 JSON 字符串。

> **语法:**json . loads(JSON _ string)
> **参数:**它以 JSON 字符串为参数。
> **返回类型:**返回 python 字典对象。

*   **json.dumps():** json.dumps()函数存在于 python 内置的‘JSON’模块中。该函数用于将 Python 对象转换为 JSON 字符串。

> **语法:** json.dumps(object)
> **参数:**它以 Python Object 为参数。
> **返回类型:**返回 JSON 字符串。

*   **update():** 此方法使用另一个字典对象或可迭代键/值对中的元素更新字典。

> **语法:**dict . update([其他])
> **参数:**采用另一个字典或可迭代的键/值对。
> **返回类型:**不返回。

**示例 1:** 更新 JSON 字符串。

## 蟒蛇 3

```py
# Python program to update
# JSON

import json

# JSON data:
x =  '{ "organization":"GeeksForGeeks",
        "city":"Noida",
        "country":"India"}'

# python object to be appended
y = {"pin":110096}

# parsing JSON string:
z = json.loads(x)

# appending the data
z.update(y)

# the result is a JSON string:
print(json.dumps(z))
```

**输出:**

> {“pin”:110096，“organization”:“GeeksForGeeks”、“country”:“India”、“city”:“Noida”}

**示例 2:** 更新 JSON 文件。假设 JSON 文件如下所示。

![python-json](img/a47e5812d815159f11317d74217dc4de.png)

我们想在 *emp_details* 之后再增加一个 JSON 数据。下面是实现。

## 蟒蛇 3

```py
# Python program to update
# JSON

import json

# function to add to JSON
def write_json(new_data, filename='data.json'):
    with open(filename,'r+') as file:
          # First we load existing data into a dict.
        file_data = json.load(file)
        # Join new_data with file_data inside emp_details
        file_data["emp_details"].append(new_data)
        # Sets file's current position at offset.
        file.seek(0)
        # convert back to json.
        json.dump(file_data, file, indent = 4)

    # python object to be appended
y = {"emp_name":"Nikhil",
     "email": "nikhil@geeksforgeeks.org",
     "job_profile": "Full Time"
    }

write_json(y)
```

**输出:**

![python-append-json](img/f729562dc982c82c00e0bf2673641330.png)