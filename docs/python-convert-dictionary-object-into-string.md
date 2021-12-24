# Python |将字典对象转换为字符串

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-object-to-string/](https://www.geeksforgeeks.org/python-convert-dictionary-object-into-string/)

字典是一个重要的容器，几乎用于日常编程和网络开发的每一个代码中，它的使用越多，就越需要掌握它，因此对它的操作的知识是必要的。
我们来看看字典变成字符串的不同方式。
**方法#1:使用 json.dumps()**
json.dumps()是 json 库中的一个内置函数。它比 pickle 有优势，因为它有跨平台支持。

## 蟒蛇 3

```py
# Python code to demonstrate
# to convert dictionary into string
# using json.dumps()

import json

# initialising dictionary
test1 = { "testname" : "akshat",
          "test2name" : "manjeet",
          "test3name" : "nikhil"}

# print original dictionary
print (type(test1))
print ("initial dictionary = ", test1)

# convert dictionary into string
# using json.dumps()
result = json.dumps(test1)

# printing result as string
print ("\n", type(result))
print ("final string = ", result)
```

**Output:**

```py
 initial dictionary = {‘testname’: ‘akshat’, ‘test2name’: ‘manjeet’, ‘test3name’: ‘nikhil’}
 <class>final string = {“testname”: “akshat”, “test2name”: “manjeet”, “test3name”: “nikhil”}</class> 
```

**方法#2:使用 str()**
str()函数将指定的值转换为字符串。

## 蟒蛇 3

```py
# Python code to demonstrate
# to convert dictionary into string
# using str()

# initialising dictionary
test1 = { "testname" : "akshat",
          "test2name" : "manjeet",
          "test3name" : "nikhil"}

# print original dictionary
print (type(test1))
print ("initial dictionary = ", test1)

# convert dictionary into string
# using str
result = str(test1)

# print resulting string
print ("\n", type(result))
print ("final string = ", result)
```

**Output:**

```py
 initial dictionary = {‘test2name’: ‘manjeet’, ‘testname’: ‘akshat’, ‘test3name’: ‘nikhil’}
 <class>final string = {‘test2name’: ‘manjeet’, ‘testname’: ‘akshat’, ‘test3name’: ‘nikhil’}</class> 
```