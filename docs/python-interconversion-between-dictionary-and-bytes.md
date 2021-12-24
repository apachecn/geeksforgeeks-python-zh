# Python |字典和字节的相互转换

> 原文:[https://www . geesforgeks . org/python-字典和字节之间的相互转换/](https://www.geeksforgeeks.org/python-interconversion-between-dictionary-and-bytes/)

数据之间的相互转换非常流行，这篇特别的文章讨论了如何将字典相互转换成字节，反之亦然。让我们看看可以帮助我们完成这项特殊任务的方法。

**方法:使用`encode() + dumps() + decode() + loads()`**
编码和转储功能一起执行将字典转换为字符串，然后转换为相应字节值的任务。这可以使用解码和加载函数进行相互转换，该函数从字节返回字符串，并再次将其转换为字典。

```py
# Python3 code to demonstrate working of
# Interconversion between Dictionary and Bytes
# Using encode() + dumps() + decode() + loads()
import json

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using encode() + dumps() to convert to bytes
res_bytes = json.dumps(test_dict).encode('utf-8')

# printing type and binary dict 
print("The type after conversion to bytes is : " + str(type(res_bytes)))
print("The value after conversion to bytes is : " + str(res_bytes))

# using decode() + loads() to convert to dictionary
res_dict = json.loads(res_bytes.decode('utf-8'))

# printing type and dict 
print("The type after conversion to dict is : " + str(type(res_dict)))
print("The value after conversion to dict is : " + str(res_dict))
```

**Output :**

```py
The original dictionary is : {'Gfg': 1, 'best': 3, 'is': 2}
The type after conversion to bytes is : <class 'bytes'>
The value after conversion to bytes is : b'{"Gfg": 1, "best": 3, "is": 2}'
The type after conversion to dict is : <class 'dict'>
The value after conversion to dict is : {'Gfg': 1, 'best': 3, 'is': 2}

```