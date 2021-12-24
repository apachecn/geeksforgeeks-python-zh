# 如何从 Python 函数返回 json 对象？

> 原文:[https://www . geeksforgeeks . org/如何从 python 函数返回-a-JSON-object/](https://www.geeksforgeeks.org/how-to-return-a-json-object-from-a-python-function/)

**[【JSON】](https://www.geeksforgeeks.org/working-with-json-data-in-python/)**的全形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 json 的内置包支持 JSON，这个模块可以用来将 python 字典转换成 JSON 对象。在 Python 中字典是用来获取它的等价 JSON 对象的。****

### ******进场:******

*   ****导入模块****
*   ****创建函数****
*   ****创建词典****
*   ****使用 [**转储()**](https://www.geeksforgeeks.org/json-dumps-in-python/) 方法将字典转换为 JSON 对象****
*   ****返回 JSON 对象****

> *******语法:** json.dumps(obj，* skipkeys = False，确保 _ascii=True，check_circular=True，allow_nan=True，cls=None，缩进=None，分隔符=None，默认值=None，sort _ keys = False，**kw)*****

****下面给出了使用上述方法的实现:****

******例 1:******

## ****蟒蛇 3****

```
**# Import Module
import json

# Create geeks function

def geeks():

    # Define Variable
    language = "Python"
    company = "GeeksForGeeks"
    Itemid = 1
    price = 0.00

    # Create Dictionary
    value = {
        "language": language,
        "company": company,
        "Itemid": Itemid,
        "price": price
    }

    # Dictionary to JSON Object using dumps() method
    # Return JSON Object
    return json.dumps(value)

# Call Function and Print it.
print(geeks())**
```

******输出:******

> ****{“语言”:“Python”，“公司”:“GeeksForGeeks”，“Itemid”:1，“价格”:0.0}****

******示例 2:** 使用列表作为字典值。****

## ****蟒蛇 3****

```
**# Import Module
import json

# Create geeks function

def geeks():

    # Create Dictionary
    value = {
        "firstName": "Pawan",
        "lastName": "Gupta",
        "hobbies": ["playing", "problem solving", "coding"],
        "age": 20,
        "children": [
            {
                "firstName": "mohan",
                "lastName": "bansal",
                "age": 15
            },
            {
                "firstName": "prerna",
                "lastName": "Doe",
                "age": 18
            }
        ]
    }

    # Dictionary to JSON Object using dumps() method
    # Return JSON Object
    return json.dumps(value)

# Call Function and Print it.
print(geeks())**
```

******输出:******

> ****{“first name”:“Pawan”、“last name”:“Gupta”、“兴趣爱好”:[“玩耍”、“解决问题”、“编码”]、“年龄”:20 岁、“儿童”:[{“first name”:“Mohan”、“last name”:“ban sal”、“年龄”:15}、{“first name”:“pre RNA”、“last name”:“Doe”、“年龄:18}]}****