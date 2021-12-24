# Python |给字典添加新键

> 原文:[https://www . geesforgeks . org/python-add-new-key-to-a-dictionary/](https://www.geeksforgeeks.org/python-add-new-keys-to-a-dictionary/)

[Python 中的字典](https://www.geeksforgeeks.org/python-dictionary/)是一个无序的数据值集合，用于像地图一样存储数据值，与其他只保存单个值作为元素的数据类型不同，字典保存`key:value` 对。

字典中提供了键值，以使其更加优化。字典中的每个键值对由冒号 **`:`** 分隔，而每个键由“逗号”分隔。字典的键必须是唯一的并且是不可变的数据类型，例如字符串、整数和元组，但是键值可以重复并且是任何类型。

让我们看看向字典添加新键的所有不同方法。

先创建一个字典。

```
# Let's create a dictionary, the functional way

# Create your dictionary class
class my_dictionary(dict):

    # __init__ function
    def __init__(self):
        self = dict()

    # Function to add key:value
    def add(self, key, value):
        self[key] = value

# Main Function
dict_obj = my_dictionary()

dict_obj.add(1, 'Geeks')
dict_obj.add(2, 'forGeeks')

print(dict_obj)
```

**输出:**

```
{1: 'Geeks', 2: 'forGeeks'}
```

**方法#1:** 使用下标符号

此方法将通过为一个键赋值，在字典上创建一个新的键/值对。如果键不存在，它将被添加并指向该值。如果该键存在，它所指向的当前值将被覆盖。

```
dict = {'key1':'geeks', 'key2':'fill_me'}
print("Current Dict is: ", dict)

# using the subscript notation
# Dictionary_Name[New_Key_Name] = New_Key_Value
dict['key2'] = 'for'
dict['key3'] = 'geeks'
print("Updated Dict is: ", dict)
```

**输出:**

```
Current Dict is:  {'key1': 'geeks', 'key2': 'fill_me'}
Updated Dict is:  {'key3': 'geeks', 'key1': 'geeks', 'key2': 'for'}
```

**方法 2:** 使用`update()`方法

当我们需要更新/添加大量的键/值到字典中时，`update()`方法是合适的。

```
dict = {'key1':'geeks', 'key2':'for'}
print("Current Dict is: ", dict)

# adding key3
dict.update({'key3':'geeks'})
print("Updated Dict is: ", dict)

# adding dict1 (key4 and key5) to dict
dict1 = {'key4':'is', 'key5':'fabulous'}
dict.update(dict1)
print(dict)

# by assigning 
dict.update(newkey1 ='portal')
print(dict)
```

**输出:**

```
Current Dict is:  {'key2': 'for', 'key1': 'geeks'}
Updated Dict is:  {'key2': 'for', 'key3': 'geeks', 'key1': 'geeks'}

{'key4': 'is', 'key2': 'for', 'key5': 'fabulous', 'key3': 'geeks', 'key1': 'geeks'}

{'key3': 'geeks', 'newkey1': 'portal', 'key1': 'geeks',
        'key4': 'is', 'key2': 'for', 'key5': 'fabulous'}
```

**方法#3:** `__setitem__` 向字典添加键值对的方法

应避免使用 `__setitem__` 方法，因为其性能较差(计算效率低)。

```
dict = {'key1':'geeks', 'key2':'for'}

# using __setitem__ method
dict.__setitem__('newkey2', 'GEEK')
print(dict)
```

**输出:**

```
{'key2': 'for', 'newkey2': 'GEEK', 'key1': 'geeks'}
```

**方法#4:** 使用*运算符

使用这种方法，我们可以将旧字典和新的键/值对合并到另一个字典中。

```
dict = {'a': 1, 'b': 2}

# will create a new dictionary
new_dict = {**dict, **{'c': 3}}

print(dict)
print(new_dict)
```

**输出:**

```
{'b': 2, 'a': 1}
{'b': 2, 'c': 3, 'a': 1}
```