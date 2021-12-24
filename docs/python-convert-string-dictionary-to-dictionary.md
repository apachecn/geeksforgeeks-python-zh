# Python |将字符串字典转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-string-dictionary-to-dictionary/](https://www.geeksforgeeks.org/python-convert-string-dictionary-to-dictionary/)

数据类型的相互转换已经被讨论了很多次，并且已经成为一个很受欢迎的解决问题。本文讨论了另一个字典的相互转换问题，即字符串格式到字典的转换。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`json.loads()`**

这个任务可以很容易地使用 python json 库的内置函数来执行，该函数将有效字典的字符串转换成 JSON 形式，Python 中的字典。

```py
# Python3 code to demonstrate
# convert dictionary string to dictionary
# using json.loads()
import json

# initializing string 
test_string = '{"Nikhil" : 1, "Akshat" : 2, "Akash" : 3}' 

# printing original string 
print("The original string : " + str(test_string))

# using json.loads()
# convert dictionary string to dictionary
res = json.loads(test_string)

# print result
print("The converted dictionary : " + str(res))
```

**Output :**

```py
The original string : {"Nikhil" : 1, "Akshat" : 2, "Akash" : 3}
The converted dictionary : {'Nikhil': 1, 'Akshat': 2, 'Akash': 3}

```

**方法 2:使用`ast.literal_eval()`**

上述方法也可用于执行类似的转换。函数比 eval 函数更安全，也可用于字典以外的所有数据类型的相互转换。

```py
# Python3 code to demonstrate
# convert dictionary string to dictionary
# using ast.literal_eval()
import ast

# initializing string 
test_string = '{"Nikhil" : 1, "Akshat" : 2, "Akash" : 3}' 

# printing original string 
print("The original string : " + str(test_string))

# using ast.literal_eval()
# convert dictionary string to dictionary
res = ast.literal_eval(test_string)

# print result
print("The converted dictionary : " + str(res))
```

**Output :**

```py
The original string : {"Nikhil" : 1, "Akshat" : 2, "Akash" : 3}
The converted dictionary : {'Nikhil': 1, 'Akshat': 2, 'Akash': 3}

```