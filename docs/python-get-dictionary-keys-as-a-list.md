# Python |获取字典键作为列表

> 原文:[https://www . geesforgeks . org/python-get-dictionary-key-as-list/](https://www.geeksforgeeks.org/python-get-dictionary-keys-as-a-list/)

给定一个字典，编写一个 Python 程序，以列表的形式获取字典键。

**示例:**

```
Input : {1:'a', 2:'b', 3:'c'}
Output : [1, 2, 3]

Input : {'A' : 'ant', 'B' : 'ball'}
Output : ['A', 'B']

```

**方法#1 :** 使用`**dict.keys()**`【针对 Python 2.x】

```
# Python program to get 
# dictionary keys as list

def getList(dict):
    return dict.keys()

# Driver program
dict = {1:'Geeks', 2:'for', 3:'geeks'}
print(getList(dict))
```

**Output:**

```
[1, 2, 3]

```

**进场#2 :** 幼稚进场。

```
# Python program to get 
# dictionary keys as list

def getList(dict):
    list = []
    for key in dict.keys():
        list.append(key)

    return list

# Driver program
dict = {1:'Geeks', 2:'for', 3:'geeks'}
print(getList(dict))
```

**Output:**

```
[1, 2, 3]

```

**方法#3 :** 对列表进行类型转换

```
# Python program to get 
# dictionary keys as list

def getList(dict):

    return list(dict.keys())

# Driver program
dict = {1:'Geeks', 2:'for', 3:'geeks'}
print(getList(dict))
```

**Output:**

```
[1, 2, 3]

```

**方法#4 :** 用**解包***
用*解包适用于任何可迭代的对象，并且由于字典在迭代时会返回它们的键，因此您可以通过在列表文本中使用它来轻松创建列表。

```
# Python program to get 
# dictionary keys as list

def getList(dict):

    return [*dict]

# Driver program
dict = {'a': 'Geeks', 'b': 'For', 'c': 'geeks'}
print(getList(dict))
```

**Output:**

```
['c', 'a', 'b']

```

**方法#5 :** 使用`itemgetter`
`itemgetter`从运算符模块返回一个可调用对象，该对象使用操作数的`__getitem__()`方法从其操作数中提取项。然后将该方法映射到`dict.items()`并将它们类型化到列表中。

```
# Python program to get 
# dictionary keys as list
from operator import itemgetter

def getList(dict):

    return list(map(itemgetter(0), dict.items()))

# Driver program
dict = {'a': 'Geeks', 'b': 'For', 'c': 'geeks'}
print(getList(dict))
```

**Output:**

```
['b', 'a', 'c']

```