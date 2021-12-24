# Python–将字典列表转换为 JSON

> 原文:[https://www . geesforgeks . org/python-convert-list-dictionary-to-JSON/](https://www.geeksforgeeks.org/python-convert-list-of-dictionaries-to-json/)

在本文中，我们将讨论如何将字典列表转换为 python 中的 JSON

## 方法 1:使用 [json.dumps()](https://www.geeksforgeeks.org/json-dumps-in-python/)

这个函数将把字典列表转换成 JSON。

**语法:**

```py
json.dumps(dict, indent)
```

**参数:**

*   字典–应该转换为 JSON 对象的字典的名称。
*   缩进–定义缩进的单位数

**示例:**创建员工数据字典列表并转换为 JSON 的 Python 程序

## 蟒蛇 3

```py
# import json module
import json

# list of dictionaries of employee data
data = [{"id": ("1", "2", "3"), "name": ("bhanu", "sivanagulu"), 
         "department": ("HR", "IT")},
        {"id": ("4", "5", "6"), "name": ("sai", "poori"),
         "department": ("HR", "IT")},
        {"id": ("7", "8", "9"), "name": ("teja", "gowtam"),
         "department": ("finance", "IT")},
        {"id": ("10", "11", "12"), "name": ("sai", "jyothi"),
         "department": ("business", "IT")},
        {"id": ("13", "14", "15"), "name": ("prudhvi", "nagendram"),
         "department": ("business", "IT")}]

# convert into json
final = json.dumps(data, indent=2)

# display
print(final)
```

**输出**:

```py
[
  {
    "id": [
      "1",
      "2",
      "3"
    ],
    "name": [
      "bhanu",
      "sivanagulu"
    ],
    "department": [
      "HR",
      "IT"
    ]
  },
  {
    "id": [
      "4",
      "5",
      "6"
    ],
    "name": [
      "sai",
      "poori"
    ],
    "department": [
      "HR",
      "IT"
    ]
  },
  {
    "id": [
      "7",
      "8",
      "9"
    ],
    "name": [
      "teja",
      "gowtam"
    ],
    "department": [
      "finance",
      "IT"
    ]
  },
  {
    "id": [
      "10",
      "11",
      "12"
    ],
    "name": [
      "sai",
      "jyothi"
    ],
    "department": [
      "business",
      "IT"
    ]
  },
  {
    "id": [
      "13",
      "14",
      "15"
    ],
    "name": [
      "prudhvi",
      "nagendram"
    ],
    "department": [
      "business",
      "IT"
    ]
  }
]
```

## 方法二:使用 [json.dump()](https://www.geeksforgeeks.org/json-dump-in-python/)

这将把转换后的 JSON 数据写入文件。

**语法:**

```py
json.dump(dict, file_pointer)
```

**参数:**

*   字典–应该转换为 JSON 对象的字典的名称。
*   文件指针–以写入或追加模式打开的文件的指针。

**语法:**

```py
with open("mydata.json", "w") as final:
   json.dump(data, final)
```

其中 mydata 是新的 JSON 文件。最后，我们必须下载创建的 JSON 文件

**语法:**

```py
files.download('mydata.json')
```

**示例:**

## 蟒蛇 3

```py
# import json module
from google.colab import files
import json

# list of dictionaries of employee data
data = [{"id": ("1", "2", "3"), "name": ("bhanu", "sivanagulu"),
         "department": ("HR", "IT")},
        {"id": ("4", "5", "6"), "name": ("sai", "poori"),
         "department": ("HR", "IT")},
        {"id": ("7", "8", "9"), "name": ("teja", "gowtam"),
         "department": ("finance", "IT")},
        {"id": ("10", "11", "12"), "name": ("sai", "jyothi"),
         "department": ("business", "IT")},
        {"id": ("13", "14", "15"), "name": ("prudhvi", "nagendram"),
         "department": ("business", "IT")}]

# convert into json
# file name is mydata
with open("mydata.json", "w") as final:
    json.dump(data, final)

# download the json file
files.download('mydata.json')
```

**输出:**

> [{"id": ["1 "、" 2 "、" 3"]、"姓名":["bhanu "、" sivanagulu"]、"部门":["HR "、" IT"]}、{"id": ["4 "、" 5 "、" 6"]、"姓名":["sai "、" poori"]、"部门":["HR "、" IT"]}、{"id": ["7 "、" 8 "、" 9"]、"姓名":["teja "、" gowtam"]、"部门":["财务"、" IT"]}、{"id " "