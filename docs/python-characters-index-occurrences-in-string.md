# Python–字符串中的字符索引出现次数

> 原文:[https://www . geesforgeks . org/python-characters-index-occurs-in-string/](https://www.geeksforgeeks.org/python-characters-index-occurrences-in-string/)

有时，在使用 Python Strings 时，我们可能会遇到一个问题，需要检查所有的字符索引。它们出现的位置。这种应用可以出现在许多领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用`set() + regex + list comprehension + replace()`**
上述功能的组合可用于执行该任务。在这种情况下，set()用于获取必须计算其频率的元素。相应地，组装到字典的任务是使用正则表达式函数和列表理解来执行的。

```py
# Python3 code to demonstrate working of 
# Characters Index occurrences in String
# Using regex + set() + list comprehension + replace()
import re 

# initializing string
test_str = "Gfg is best for geeks"

# printing original string
print("The original string is : " + test_str)

# Characters Index occurrences in String
# Using regex + set() + list comprehension + replace()
temp = set(test_str.replace(' ', ''))
res = {ele: [sub.start() for sub in re.finditer(ele, test_str)] for ele in temp}

# printing result 
print("Characters frequency index dictionary : " + str(res)) 
```

**Output :**

```py
The original string is : Gfg is best for geeks
Characters frequency index dictionary : {'g': [2, 16], 'k': [19], 't': [10], 'G': [0], 'b': [7], 'i': [4], 'r': [14], 'f': [1, 12], 's': [5, 9, 20], 'o': [13], 'e': [8, 17, 18]}

```