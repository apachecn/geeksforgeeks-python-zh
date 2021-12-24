# Python |将字节串键:字典的值对转换为字符串

> 原文:[https://www . geesforgeks . org/python-convert-bytestring-key value-对字典到字符串/](https://www.geeksforgeeks.org/python-convert-bytestring-keyvalue-pair-of-dictionary-to-string/)

给定一个关键字:值对为字节串的字典，任务是将关键字:值对转换为字符串。

**示例:**

```
Input: {b'EmplId': b'12345', b'Name': b'Paras', b'Company': b'Cyware' }
Output: {'EmplId': '12345', 'Name': 'Paras', 'Company': 'Cyware'}

Input: {b'Key1': b'Geeks', b'Key2': b'For', b'Key3': b'Geek' }
Output: {'Key1':'Geeks', 'Key2':'For', 'Key3':'Geek' }

```

**方法一:**靠字典理解

```
# Python Code to convert ByteString key:value 
# pair of dictionary to String.

# Initialising dictionary 
x = {b'EmplId': b'12345', b'Name': b'Paras', b'Company': b'Cyware'}

# Converting
x = { y.decode('ascii'): x.get(y).decode('ascii') for y in x.keys() }

# printing converted dictionary
print(x)
```

**Output:**

```
{'Name': 'Paras', 'EmplId': '12345', 'Company': 'Cyware'}

```

**方法#2:** 通过迭代键和值

```
# Python Code to convert ByteString key:value 
# pair of dictionary to String.

# Initialising dictionary 
x = {b'EmplId': b'12345', b'Name': b'Paras', b'Company': b'Cyware'}

# Initialising empty dictionary 
y = {}

# Converting
for key, value in x.items():
    y[key.decode("utf-8")] = value.decode("utf-8")

# printing converted dictionary
print(y)
```

**Output:**

```
{'Company': 'Cyware', 'Name': 'Paras', 'EmplId': '12345'}

```