# 在 Python 中的字典中添加一个键:值对

> 原文:[https://www . geesforgeks . org/add-a-key value-pair-to-dictionary-in-python/](https://www.geeksforgeeks.org/add-a-keyvalue-pair-to-dictionary-in-python/)

[Python 中的 Dictionary](https://www.geeksforgeeks.org/python-dictionary/) 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 key:value pair。

在使用字典时，有时，我们需要在字典中添加或修改键/值。让我们看看如何在 Python 中给字典添加一个`key:value`对。

**代码#1:** 使用下标符号

这个方法将在字典上创建一个新的键:值对，方法是给这个键赋值。

```py
# Python program to add a key:value pair to dictionary

dict = {'key1':'geeks', 'key2':'for'} 
print("Current Dict is: ", dict) 

# using the subscript notation 
# Dictionary_Name[New_Key_Name] = New_Key_Value 

dict['key3'] = 'Geeks'
dict['key4'] = 'is'
dict['key5'] = 'portal'
dict['key6'] = 'Computer'
print("Updated Dict is: ", dict)
```

**Output:**

> 当前 Dict 为:{'key2': 'for '，' key1': 'geeks'}
> 更新后的 Dict 为:{'key3': 'Geeks '，' key5': 'portal '，' key6': 'Computer '，' key4': 'is '，' key1': 'geeks '，' key2': 'for'}

**代码#2:** 使用 update()方法

```py
dict = {'key1':'geeks', 'key2':'for'} 
print("Current Dict is: ", dict) 

# adding dict1 (key3, key4 and key5) to dict 
dict1 = {'key3':'geeks', 'key4':'is', 'key5':'fabulous'} 
dict.update(dict1) 

# by assigning 
dict.update(newkey1 ='portal') 
print(dict) 
```

**Output:**

> 当前 Dict 为:{'key2': 'for '，' key1': 'geeks ' }
> { ' new key 1 ':' portal '，' key4': 'is '，' key2': 'for '，' key 1 ':' geeks '，' key5 ':'神话般'，' key3': 'geeks'}

**代码#3:** 以键:值为输入

```py
# Let's add key:value to a dictionary, the functional way 

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

# Taking input key = 1, value = Geek
dict_obj.key = input("Enter the key: ")
dict_obj.value = input("Enter the value: ")

dict_obj.add(dict_obj.key, dict_obj.value) 
dict_obj.add(2, 'forGeeks') 

print(dict_obj) 
```

**输出:**

```py
 {'1': 'Geeks', 2: 'forGeeks'}
```