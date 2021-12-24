# Python–将字符串转换为字典列表

> 原文:[https://www . geesforgeks . org/python-convert-string-to-list-dictionary/](https://www.geeksforgeeks.org/python-convert-string-to-list-of-dictionaries/)

给定字符串格式的字典列表，转换为实际的字典列表。

> **输入**:test _ str =[" { ' Gfg ':3，' Best' : 8}，{'Gfg' : 4，' Best' : 8}]"]
> **输出**:[{ ' Gfg ':3，' Best' : 8}，{'Gfg': 4，' Best ':8 }]
> **解释**:字符串转换为字典列表。
> 
> **输入**:test _ str =[" { ' Gfg ':3，' Best' : 8}]"]
> **输出**:[{ ' Gfg ':3，' Best ':8 }]
> **解释**:字符串转换为字典列表。

**方法#1:使用 json.loads() + replace()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 replace()替换内部字符串，并使用 loads()创建字典列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert String to List of dictionaries
# Using json.loads + replace()
import json

# initializing string
test_str = ["[{'Gfg' : 3, 'Best' : 8}, {'Gfg' : 4, 'Best' : 9}]"]

# printing original string
print("The original string is : " + str(test_str))

# replace() used to replace strings 
# loads() used to convert 
res = [json.loads(idx.replace("'", '"')) for idx in test_str]

# printing result 
print("Converted list of dictionaries : " + str(res)) 
```

**Output**

```py
The original string is : ["[{'Gfg' : 3, 'Best' : 8}, {'Gfg' : 4, 'Best' : 9}]"]
Converted list of dictionaries : [[{'Gfg': 3, 'Best': 8}, {'Gfg': 4, 'Best': 9}]]

```

**方法 2:使用 eval()**

这是执行这项任务的方法之一。eval()在内部评估数据类型并返回所需的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert String to List of dictionaries
# Using json.loads + replace()

# initializing string
test_str = "[{'Gfg' : 3, 'Best' : 8}, {'Gfg' : 9, 'Best' : 9}]"

# printing original string
print("The original string is : " + str(test_str))

# eval() used to convert 
res = list(eval(test_str))

# printing result 
print("Converted list of dictionaries : " + str(res)) 
```

**Output**

```py
The original string is : [{'Gfg' : 3, 'Best' : 8}, {'Gfg' : 9, 'Best' : 9}]
Converted list of dictionaries : [{'Gfg': 3, 'Best': 8}, {'Gfg': 9, 'Best': 9}]

```