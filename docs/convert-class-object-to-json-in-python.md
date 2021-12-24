# 将类对象转换为 Python 中的 JSON

> 原文:[https://www . geesforgeks . org/convert-class-object-to-JSON-in-python/](https://www.geeksforgeeks.org/convert-class-object-to-json-in-python/)

类对象到 JSON 的转换是使用 Python 中的 [json](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/) 包完成的。 [json.dumps()](https://www.geeksforgeeks.org/json-dumps-in-python/) 将 Python 对象转换为 json 字符串。每个 Python 对象都有一个由 __dict__ 表示的属性，它存储对象的属性。

1.  对象首先使用 __dict__ 属性转换为字典格式。
2.  这个新创建的字典作为参数传递给 [json.dumps()](https://www.geeksforgeeks.org/json-dumps-in-python/) ，然后产生一个 json 字符串。

> **语法:** json.dumps(对象对象)
> 
> **参数:**需要字典对象。
> 
> **返回:** json 字符串

**跟随 python 代码将一个 python 类 Student 对象转换为 JSON。**

## 蟒蛇 3

```py
# import required packages
import json

# custom class
class Student:
    def __init__(self, roll_no, name, batch):
        self.roll_no = roll_no
        self.name = name
        self.batch = batch

class Car:
    def __init__(self, brand, name, batch):
        self.brand = brand
        self.name = name
        self.batch = batch

# main function
if __name__ == "__main__":

    # create two new student objects
    s1 = Student("85", "Swapnil", "IMT")
    s2 = Student("124", "Akash", "IMT")

    # create two new car objects
    c1 = Car("Honda", "city", "2005")
    c2 = Car("Honda", "Amaze", "2011")

    # convert to JSON format
    jsonstr1 = json.dumps(s1.__dict__)
    jsonstr2 = json.dumps(s2.__dict__)
    jsonstr3 = json.dumps(c1.__dict__)
    jsonstr4 = json.dumps(c2.__dict__)

    # print created JSON objects
    print(jsonstr1)
    print(jsonstr2)
    print(jsonstr3)
    print(jsonstr4)
```

**输出:**

```py
{"roll_no": "85", "name": "Swapnil", "batch": "IMT"}
{"roll_no": "124", "name": "Akash", "batch": "IMT"}
{"brand": "Honda", "name": "city", "batch": "2005"}
{"brand": "Honda", "name": "Amaze", "batch": "2011"}
```