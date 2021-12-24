# Python-JSON 中自定义对象的编码和解码

> 原文:[https://www . geesforgeks . org/编解码-python 中的自定义对象-json/](https://www.geeksforgeeks.org/encoding-and-decoding-custom-objects-in-python-json/)

**[JSON](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/)** 我们知道代表 **JavaScript 对象符号**。它是一种轻量级的数据交换格式，已经成为网络上最流行的数据交换媒介。它受欢迎的原因是它既可读又易于机器解析和生成。此外，它也是 REST APIs 最广泛使用的格式。

**注意:**更多信息请参考[用 Python 写解析 JSON】](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/)

## 入门指南

Python 提供了一个内置的`json`库来处理 JSON 对象。您只需要在 Python 程序中使用下面的行导入 JSON 模块，并开始使用它的功能。

```py
import json
```

现在 JSON 模块提供了很多功能，我们将只讨论其中的两种方法。它们是 **[转储](https://www.geeksforgeeks.org/json-dumps-in-python/)** 和 **[装载](https://www.geeksforgeeks.org/json-load-in-python/)** 。将 python 对象转换为 json 对象的过程称为 **JSON 序列化**或**编码**，将 JSON 对象转换为 Python 对象的反向过程称为**反序列化**或**解码**

对于编码，我们使用`json.dumps()`，对于解码，我们将使用`json.loads()`。因此很明显，dumps 方法会将 python 对象转换为序列化的 JSON 字符串，loads 方法会从序列化的 JSON 字符串解析 Python 对象。

**注:**

*   这里值得一提的是，在序列化过程中创建的 JSON 对象只是一个 Python 字符串，这就是为什么您会在本文中发现术语“JSON 对象”和“JSON 字符串”可以互换使用的原因
*   同样重要的是要注意，JSON 对象对应于 Python 中的字典。因此，当您使用 loads 方法时，默认情况下会返回一个 Python 字典(除非您改变这种行为，如本文的自定义解码部分所述)

**示例:**

```py
import json

# A basic python dictionary
py_object = {"c": 0, "b": 0, "a": 0} 

# Encoding
json_string = json.dumps(py_object)
print(json_string)
print(type(json_string))

# Decoding JSON
py_obj = json.loads(json_string) 
print()
print(py_obj)
print(type(py_obj))
```

**输出:**

```py
{"c": 0, "b": 0, "a": 0}
<class 'str'>

{'c': 0, 'b': 0, 'a': 0}
<class 'dict'>
```

虽然我们上面看到的是一个非常简单的例子。但是你有没有想过在定制对象的情况下会发生什么？在这种情况下，上面的代码将不起作用，我们将得到类似–**类型错误的错误:SampleClass 类型的对象不是 JSON 可序列化的**。那怎么办？别担心，我们会进入下面的部分。

## 自定义对象的编码和解码

在这种情况下，我们需要付出更多的努力来使它们序列化。让我们看看如何做到这一点。假设我们有一个用户定义的类 **Student** ，我们希望将其设为 JSON 可序列化。最简单的方法是在我们的类中定义一个方法，提供我们类实例的 JSON 版本。

**示例:**

```py
import json

class Student:
    def __init__(self, name, roll_no, address):
        self.name = name
        self.roll_no = roll_no
        self.address = address

    def to_json(self):
        '''
        convert the instance of this class to json
        '''
        return json.dumps(self, indent = 4, default=lambda o: o.__dict__)

class Address:
    def __init__(self, city, street, pin):
        self.city = city
        self.street = street
        self.pin = pin

address = Address("Bulandshahr", "Adarsh Nagar", "203001")
student = Student("Raju", 53, address)

# Encoding
student_json = student.to_json()
print(student_json)
print(type(student_json))

# Decoding
student = json.loads(student_json)
print(student)
print(type(student))
```

**输出:**

> {
> 【名称】:【拉朱】、
> 【roll _ no】:53、
> 【地址】:{
> 【城市】:【布兰沙尔】、
> 【街道】:【阿达什纳加尔】、
> 【pin】:【203001】
> }
> }
> <类‘str’>
> 
> { '姓名':' Raju '，' roll_no': 53，'地址':{'city': 'Bulandshahr '，' street': 'Adarsh Nagar '，' pin ':' 203001 ' }
> T1】类' dict' >

实现这一点的另一种方法是创建一个新的类来扩展 **JSONEncoder** ，然后将该类用作**转储**方法的参数。

**示例:**

```py
import json
from json import JSONEncoder

class Student:
    def __init__(self, name, roll_no, address):
        self.name = name
        self.roll_no = roll_no
        self.address = address

class Address:
    def __init__(self, city, street, pin):
        self.city = city
        self.street = street
        self.pin = pin

class EncodeStudent(JSONEncoder):
        def default(self, o):
            return o.__dict__

address = Address("Bulandshahr", "Adarsh Nagar", "203001")
student = Student("Raju", 53, address)

# Encoding custom object to json
# using cls(class) argument of
# dumps method
student_JSON = json.dumps(student, indent = 4,
                          cls = EncodeStudent)
print(student_JSON)
print(type(student_JSON))

# Decoding
student = json.loads(student_JSON)
print()
print(student)
print(type(student))
```

**输出:**

> {
> 【名称】:【拉朱】、
> 【roll _ no】:53、
> 【地址】:{
> 【城市】:【布兰沙尔】、
> 【街道】:【阿达什纳加尔】、
> 【pin】:【203001】
> }
> }
> <类‘str’>
> 
> { '姓名':' Raju '，' roll_no': 53，'地址':{'city': 'Bulandshahr '，' street': 'Adarsh Nagar '，' pin ':' 203001 ' }
> T1】类' dict' >

对于**自定义解码**，如果我们想将 JSON 转换成其他 Python 对象(即不是默认字典)，有一个非常简单的方法，那就是使用**加载**方法的 **object_hook** 参数。我们需要做的就是定义一个方法，该方法将定义我们希望如何处理数据，然后将该方法作为 object_hook 参数发送给 loads 方法，请参见给定代码中的。此外，加载的返回类型将不再是 Python 字典。无论我们将作为 object_hook 传入的方法的返回类型是什么，它也将成为 loads 方法的返回类型。这意味着在下面的例子中，复数将是返回类型。

```py
import json

def as_complex(dct):

    if '__complex__' in dct:
        return complex(dct['real'], dct['imag'])

    return dct

res = json.loads('{"__complex__": true, "real": 1, "imag": 2}',
           object_hook = as_complex)
print(res)
print(type(res))
```

**输出:**

```py
(1+2j)
<class 'complex'>
```