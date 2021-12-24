# Python |使用列表内容创建词典

> 原文:[https://www . geesforgeks . org/python-词典-创建-使用-列表-目录/](https://www.geeksforgeeks.org/python-dictionary-creation-using-list-contents/)

有时我们需要处理列表格式的数据，并将列表转换成字典格式。当我们处理机器学习以改变格式给出进一步的输入时，这个特殊的问题很常见。让我们讨论这种相互转换发生的某些方式。

**方法一:利用字典理解+ `zip()`**

在这个方法中，我们使用字典理解来执行迭代和逻辑部分，将所有列表绑定到一个字典中，并使用相关的键，这是通过 zip 函数来完成的。

```py
# Python3 code to demonstrate
# Dictionary creation using list contents
# using Dictionary comprehension + zip()

# initializing list
keys_list = ["key1", "key2"]
nested_name = ["Manjeet", "Nikhil"]
nested_age = [22, 21]

# printing original lists
print("The original key list : " + str(keys_list))
print("The original nested name list : " + str(nested_name))
print("The original nested age list : " + str(nested_age))

# using Dictionary comprehension + zip()
# Dictionary creation using list contents
res = {key: {'name': name, 'age': age} for key, name, age in
              zip(keys_list, nested_name, nested_age)}

# print result
print("The dictionary after construction : " + str(res))
```

**Output :**

> 原始键列表:['key1 '，' key2']
> 原始嵌套名称列表:['Manjeet '，' Nikhil']
> 原始嵌套年龄列表:[22，21]
> 构造后的字典:{'key1': {'age': 22，' name': 'Manjeet'}，' key2': {'age': 21，' name': 'Nikhil'}}

**方法二:利用字典理解+ `enumerate()`**

类似的任务可以使用由 zip 功能执行的`enumerate` 功能来执行。字典理解执行类似于上面的任务。

```py
# Python3 code to demonstrate
# Dictionary creation using list contents
# using dictionary comprehension + enumerate()

# initializing list
keys_list = ["key1", "key2"]
nested_name = ["Manjeet", "Nikhil"]
nested_age = [22, 21]

# printing original lists
print("The original key list : " + str(keys_list))
print("The original nested name list : " + str(nested_name))
print("The original nested age list : " + str(nested_age))

# using dictionary comprehension + enumerate()
# Dictionary creation using list contents
res = {val : {"name": nested_name[key], "age": nested_age[key]}
       for key, val in enumerate(keys_list)}

# print result
print("The dictionary after construction : " + str(res))
```

**Output :**

> 原始键列表:['key1 '，' key2']
> 原始嵌套名称列表:['Manjeet '，' Nikhil']
> 原始嵌套年龄列表:[22，21]
> 构造后的字典:{'key1': {'age': 22，' name': 'Manjeet'}，' key2': {'age': 21，' name': 'Nikhil'}}