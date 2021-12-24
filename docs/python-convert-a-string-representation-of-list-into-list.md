# Python |将列表的字符串表示转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-a-string-presentation-of-list-to-list/](https://www.geeksforgeeks.org/python-convert-a-string-representation-of-list-into-list/)

很多时候，我们会遇到以字符串格式找到的转储数据，并要求将其表示为实际找到的实际列表格式。这种将字符串格式的列表转换回列表来执行任务的问题在 web 开发中非常常见。让我们讨论一下实现这一点的某些方法。

**方法#1:** 使用`split()`和`strip()`

```
# Python code to demonstrate converting 
# string representation of list to list
# using strip and split

# initializing string representation of a list
ini_list = "[1, 2, 3, 4, 5]"

# printing initialized string of list and its type
print ("initial string", ini_list)
print (type(ini_list))

# Converting string to list
res = ini_list.strip('][').split(', ')

# printing final result and its type
print ("final list", res)
print (type(res))
```

**输出:**

```
initial string [1, 2, 3, 4, 5]
<class 'str'>
final list ['1', '2', '3', '4', '5']
<class 'list'>

```