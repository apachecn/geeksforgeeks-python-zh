# 将嵌套 Python 字典转换为对象

> 原文:[https://www . geesforgeks . org/convert-nested-python-dictionary-to-object/](https://www.geeksforgeeks.org/convert-nested-python-dictionary-to-object/)

让我们看看如何将一个给定的嵌套字典转换成一个对象

**方法 1 :** 使用 **`json`** 模块。我们可以通过导入 json 模块并在`json.loads()`方法中使用自定义对象钩子来解决这个特殊问题。

```py
# importing the module
import json

# declaringa a class
class obj:

    # constructor
    def __init__(self, dict1):
        self.__dict__.update(dict1)

def dict2obj(dict1):

    # using json.loads method and passing json.dumps
    # method and custom object hook as arguments
    return json.loads(json.dumps(dict1), object_hook=obj)

# initializing the dictionary  
dictionary = {'A': 1, 'B': {'C': 2},
              'D': ['E', {'F': 3}],'G':4}

# calling the function dict2obj and
# passing the dictionary as argument
obj1 = dict2obj(dictionary)

# accessing the dictionary as an object
print (obj1.A)
print(obj1.B.C)
print(obj1.D[0])
print(obj1.D[1].F)
print(obj1.G)
```

**输出**

```py
1
2
E
3
4

```