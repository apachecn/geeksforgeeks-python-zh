# Python |将列表字符串转换为字典

> 原文:[https://www . geesforgeks . org/python-converting-list-string-to-dictionary/](https://www.geeksforgeeks.org/python-converting-list-string-to-dictionary/)

关于数据类型之间相互转换的另一个问题是将列表字符串转换为键和值的字典。在机器学习领域，这个特殊的问题可能发生在我们需要将大量的字符串数据转换成字典进行预处理的地方。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用字典理解+ `split()`**
字典理解可用于字典的构造，拆分功能可用于在列表中执行必要的拆分，以获得字典的有效键值对。

```py
# Python3 code to demonstrate
# Converting list string to dictionary 
# Using dictionary comprehsion + split()

# initializing string
test_string = '[Nikhil:1, Akshat:2, Akash:3]'

# printing original string
print("The original string : " + str(test_string))

# using dictionary comprehsion + split()
# Converting list string to dictionary 
res = {sub.split(":")[0]: sub.split(":")[1] for sub in test_string[1:-1].split(", ")}

# print result
print("The dictionary after extraction is : " + str(res))
```

**Output :**

```py
The original string : [Nikhil:1, Akshat:2, Akash:3]
The dictionary after extraction is : {'Nikhil': '1', 'Akash': '3', 'Akshat': '2'}

```