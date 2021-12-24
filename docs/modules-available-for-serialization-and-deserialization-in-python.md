# Python 中可用于序列化和反序列化的模块

> 原文:[https://www . geesforgeks . org/modules-可用于 python 中的序列化和反序列化/](https://www.geeksforgeeks.org/modules-available-for-serialization-and-deserialization-in-python/)

Python 提供了三个不同的模块，允许我们序列化和反序列化对象:

1.  编组模块
2.  泡菜模块
3.  JSON 模块

**1。元帅舱:**是这三个中最古老的舱。主要用于 Python 模块的编译字节码的读写。甚至我们可以使用 marshal 来序列化 Python 对象，但不建议使用。它主要由解释器使用，官方文档警告 python 维护者可能会以向后不兼容的方式修改格式。

**注意:**建议永远不要解封从不受信任或未经身份验证的来源接收的数据。

**示例:**

## 蟒蛇 3

```
# importing the module
import marshal 

data = {'name': 'sunny','age': 34,'address': 'nasik'}

# dumps() return byte object stored in variable 'bytes'
bytes = marshal.dumps(data)   
print('After serialization : ', bytes)

# loads() convert byte object to value
new_data = marshal.loads(bytes)   
print('After deserialization : ', new_data)
```

**输出:**

> 序列化后:b ' \ xfb \ xda \ x04 name \ xda \ x05 sunny \ xda \ x03 age \ xe9 ″\ x00 \ x00 \ x00 \ xda \ x07 address \ xda \ x05 nasik0′
> 
> 反序列化后:{'name': 'sunny '，' age': 34，' address': 'nasik'}

**2。Pickle 模块:**这是序列化和反序列化 Python 对象的另一种方式。它以二进制格式序列化 Python 对象，因此不可读。它速度更快，并且也适用于自定义对象。Python pickle 模块是 Python 对象序列化和反序列化的更好选择。如果您不需要人类可读的格式，或者如果您需要序列化自定义对象，那么建议使用 pickle 模块。

**示例:**

## 蟒蛇 3

```
# importinig the module
import pickle

data = {'st_name': 'Sunny', 'st_id': '9607', 'st_add': 'Nasik'}
with open('data.pickle', 'wb') as f1 :        

    # converts object to byte stream(list, dict, etc.)
    pickle.dump(data, f1)      
    print('Pickling Completed...')

with open('data.pickle', 'rb') as f2 :
    print('Unpickling the data : ')

    # converts byte stream(generated through pickling)back into object
    data = pickle.load(f2)
    print(data)
```