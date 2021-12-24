# Python |用列表中的键初始化字典

> 原文:[https://www . geesforgeks . org/python-initialize-a-dictionary-with-only-key-from-list/](https://www.geeksforgeeks.org/python-initialize-a-dictionary-with-only-keys-from-a-list/)

给定一个列表，任务是通过使用给定的列表作为关键字来创建一个只有关键字的字典。

让我们看看我们可以用不同的方法来完成这项任务。

**方法#1** :通过遍历列表

```py
# Python code to initialize a dictionary
# with only keys from a list

# List of keys
keyList = ["Paras", "Jain", "Cyware"]

# initialize dictionary
d = {}

# iterating through the elements of list
for i in keyList:
    d[i] = None

print(d)
```

**Output:**

```py
{'Cyware': None, 'Paras': None, 'Jain': None}

```

**方法 2 :** 使用字典理解

```py
# Python code to initialize a dictionary
# with only keys from a list

# List of Keys
keyList = ["Paras", "Jain", "Cyware"]

# Using Dictionary comprehension
myDict = {key: None for key in keyList}
print(myDict)
```

**Output:**

```py
{'Paras': None, 'Jain': None, 'Cyware': None}

```

**方法#3 :** 使用 zip()函数

```py
# Python code to initialize a dictionary
# with only keys from a list

# List of keys
listKeys = ["Paras", "Jain", "Cyware"]

# using zip() function to create a dictionary
# with keys and same length None value 
dct = dict(zip(listKeys, [None]*len(listKeys)))

# print dict
print(dct)
```

**Output:**

```py
{'Cyware': None, 'Paras': None, 'Jain': None}

```

**方法#4 :** 使用 fromkeys()方法

```py
# Python code to initialize a dictionary
# with only keys from a list

# List of keys
Student = ["Paras", "Jain", "Cyware"]

# using fromkeys() method
StudentDict = dict.fromkeys(Student, None)

# printing dictionary
print(StudentDict)
```

**Output:**

```py
{'Cyware': None, 'Jain': None, 'Paras': None}

```