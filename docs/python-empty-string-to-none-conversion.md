# Python |空字符串到无的转换

> 原文:[https://www . geesforgeks . org/python-空字符串到无的转换/](https://www.geeksforgeeks.org/python-empty-string-to-none-conversion/)

有时，在使用机器学习时，我们会遇到空字符串，为了数据一致性，我们希望转换为无。这个和许多其他实用程序可能需要解决这个问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用λ**
这个任务可以使用λ函数来执行。在本例中，我们使用 or 运算符检查无字符串或空字符串，并用无替换空字符串。

```
# Python3 code to demonstrate working of
# Empty String to None Conversion
# Using lambda

# initializing list of strings
test_list = ["Geeks", '', "CS", '', '']

# printing original list 
print("The original list is : " + str(test_list))

# using lambda
# Empty String to None Conversion
conv = lambda i : i or None
res = [conv(i) for i in test_list]

# printing result 
print("The list after conversion of Empty Strings : " + str(res))
```

**Output :**

```
The original list is : ['Geeks', '', 'CS', '', '']
The list after conversion of Empty Strings : ['Geeks', None, 'CS', None, None]

```