# Python–将字典列表转换为列表列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-dictionary-to-list/](https://www.geeksforgeeks.org/python-convert-list-of-dictionaries-to-list-of-lists/)

有时，在使用 Python 数据时，我们会遇到这样的问题，即我们需要将字典列表转换为列表列表，这可以通过只追加一次键来简化，如果它们像大多数记录一样重复，这可以节省内存空间。这种类型的问题可能在 web 开发领域有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'Gfg': 123，' best': 10}，{'Gfg': 51，' best': 7}]
> **输出**:[' Gfg '，' best']，[123，10]，[51，7]]
> 
> **输入**:test _ list =[{ ' Gfg ':12 }]
> **输出** : [['Gfg']，[12]]

**方法#1:使用 loop + `enumerate()`**
以上方法的组合可以用来执行这个任务。在本例中，我们使用循环和蛮力执行迭代任务，并借助 enumerate()在结果列表中执行适当的追加。

```py
# Python3 code to demonstrate working of 
# Convert List of Dictionaries to List of Lists
# Using loop + enumerate()

# initializing list
test_list = [{'Nikhil' : 17, 'Akash' : 18, 'Akshat' : 20},
             {'Nikhil' : 21, 'Akash' : 30, 'Akshat' : 10},
             {'Nikhil' : 31, 'Akash' : 12, 'Akshat' : 19}]

# printing original list
print("The original list is : " + str(test_list))

# Convert List of Dictionaries to List of Lists
# Using loop + enumerate()
res = []
for idx, sub in enumerate(test_list, start = 0):
    if idx == 0:
        res.append(list(sub.keys()))
        res.append(list(sub.values()))
    else:
        res.append(list(sub.values()))

# printing result 
print("The converted list : " + str(res)) 
```

**Output :**

> 原来的列表是:[{'Akash': 18，' Nikhil': 17，' Akshat': 20}，{'Akash': 30，' Nikhil': 21，' Akshat': 10}，{'Akash': 12，' Nikhil': 31，' Akshat': 19}]
> 转换后的列表:['Akash '，' Nikhil '，' Akshat']，[18，17，20]，[30，21，10]，[12，31，19]

**方法 2:使用列表理解**
这个任务可以使用列表理解一行解决。在本例中，我们最初使用 key()提取键，使用 value()提取值。

```py
# Python3 code to demonstrate working of 
# Convert List of Dictionaries to List of Lists
# Using list comprehension

# initializing list
test_list = [{'Nikhil' : 17, 'Akash' : 18, 'Akshat' : 20},
             {'Nikhil' : 21, 'Akash' : 30, 'Akshat' : 10},
             {'Nikhil' : 31, 'Akash' : 12, 'Akshat' : 19}]

# printing original list
print("The original list is : " + str(test_list))

# Convert List of Dictionaries to List of Lists
# Using list comprehension
res = [[key for key in test_list[0].keys()], *[list(idx.values()) for idx in test_list ]]

# printing result 
print("The converted list : " + str(res)) 
```

**Output :**

> 原来的列表是:[{'Akash': 18，' Nikhil': 17，' Akshat': 20}，{'Akash': 30，' Nikhil': 21，' Akshat': 10}，{'Akash': 12，' Nikhil': 31，' Akshat': 19}]
> 转换后的列表:['Akash '，' Nikhil '，' Akshat']，[18，17，20]，[30，21，10]，[12，31，19]