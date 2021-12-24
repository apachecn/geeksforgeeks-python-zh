# Python |检查字符串是否为有效 JSON

> 原文:[https://www . geesforgeks . org/python-check-a-string-valid-JSON-or-not/](https://www.geeksforgeeks.org/python-check-whether-a-string-is-valid-json-or-not/)

给定一个字符串，任务是检查一个字符串是否是有效的 json 对象。让我们试着用不同的例子来理解这个问题。

**代码#1 :**

```py
# Python code to demonstrate
# checking whether string
# is valid json or not

import json

ini_string = "{'akshat' : 1, 'nikhil' : 2}"

# printing initial ini_string
print ("initial string", ini_string)

# checking for string
try:
    json_object = json.loads(ini_string)
    print ("Is valid json? true")
except ValueError as e:
    print ("Is valid json? false")
```

**Output:**

```py
initial string {'akshat' : 1, 'nikhil' : 2}
Is valid json? false

```

**代码#2:**

```py
# Python code to demonstrate
# checking whether string
# is valid json or not

import json

#ini_string = '{"Geek" : 1,"forGeeks" : 2}'

a = '{"name":"John", "age":31, "Salary":25000}'
b = '{ "Subjects": {"Maths":85, "Physics":90}}'

#printing initial ini_string
print ("initial strings given - \n", a, "\n", b)

#checking for string
try:
    json_object1 = json.loads(a)
    json_object2 = json.loads(b)
    print ("Is valid json? true")

except ValueError as e:
    print ("Is valid json? false")
```

**Output:**

```py
initial strings given - 
 {"name":"John", "age":31, "Salary":25000} 
 { "Subjects": {"Maths":85, "Physics":90}}
Is valid json? true

```