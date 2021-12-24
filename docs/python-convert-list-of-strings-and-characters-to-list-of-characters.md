# Python |将字符串和字符列表转换为字符列表

> 原文:[https://www . geesforgeks . org/python-convert-list-string-and-characters-to-list-characters/](https://www.geeksforgeeks.org/python-convert-list-of-strings-and-characters-to-list-of-characters/)

有时我们会遇到这样的问题:我们收到一个由字符串和混合字符组成的列表，我们需要执行的任务是将该混合列表转换为完全由字符组成的列表。让我们讨论实现这一点的某些方法。

**方法#1:使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**
在该方法中，我们只需将每个列表元素视为字符串，并迭代它们的每个字符，并将每个字符追加到新创建的目标列表中。

```py
# Python3 code to demonstrate 
# to convert list of string and characters
# to list of characters
# using list comprehension

# initializing list  
test_list = [ 'gfg', 'i', 's', 'be', 's', 't']

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension
# to convert list of string and characters
# to list of characters
res = [i for ele in test_list for i in ele]

# printing result 
print ("The list after conversion is : " +  str(res))
```

**Output:**

```py
The original list is : ['gfg', 'i', 's', 'be', 's', 't']
The list after conversion is : ['g', 'f', 'g', 'i', 's', 'b', 'e', 's', 't']

```