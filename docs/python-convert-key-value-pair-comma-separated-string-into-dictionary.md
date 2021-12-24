# Python |将键值对逗号分隔字符串转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-key-value-pair-逗号分隔-string-in-dictionary/](https://www.geeksforgeeks.org/python-convert-key-value-pair-comma-separated-string-into-dictionary/)

给定一个字符串，用逗号分隔不同的键值对，任务是将该字符串转换为字典。这些类型的问题在 web 开发中很常见，我们从查询中获取参数或者以字符串的形式获得响应。下面给出了几个解决任务的方法。

**方法一:利用词典理解**

```py
# Python3 code to demonstrate 
# converting comma separated string
# into dictionary

# Initialising string
ini_string1 = 'name = akshat, course = btech, branch = computer'

# Printing initial string
print ("Initial String", ini_string1)

# Converting string into dictionary
# using dict comprehension
res = dict(item.split("=") for item in ini_string1.split(", "))

# Printing resultant string
print ("Resultant dictionary", str(res))

```

**Output:**

> Initial String name = akshat，course = btech，branch = computer
> 结果字典{'branch ': ' computer '，' name ': ' akshat '，' course ': ' btech'}