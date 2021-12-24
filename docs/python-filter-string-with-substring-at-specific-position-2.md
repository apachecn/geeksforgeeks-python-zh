# Python |特定位置有子串的过滤字符串

> 原文:[https://www . geesforgeks . org/python-filter-string-with-substring-at-special-position-2/](https://www.geeksforgeeks.org/python-filter-string-with-substring-at-specific-position-2/)

有时，在使用 Python 字符串列表时，我们会遇到一个问题，即我们只需要提取那些在特定位置有特定子字符串的列表。这种问题可能出现在数据处理和 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+列表切片**
上述功能的组合可用于执行该特定任务。在本文中，我们使用列表切片来检查子串范围，并且在列表理解中编译提取列表的任务。

```py
# Python3 code to demonstrate 
# Filter String with substring at specific position
# using list comprehension + list slicing

# Initializing list
test_list = ['geeksforgeeks', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# Initializing substring
sub_str = 'geeks'

# Initializing range 
i, j = 0, 5

# Filter String with substring at specific position
# using list comprehension + list slicing
res = [ele for ele in test_list if ele[i: j] == sub_str]

# printing result 
print ("Filtered list : " + str(res))
```

**Output :**

```py
The original list is : ['geeksforgeeks', 'is', 'best', 'for', 'geeks']
Filtered list : ['geeksforgeeks', 'geeks']

```