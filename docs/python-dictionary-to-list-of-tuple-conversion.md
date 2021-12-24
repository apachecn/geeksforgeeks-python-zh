# Python |字典到列表的元组转换

> 原文:[https://www . geesforgeks . org/python-字典到元组列表的转换/](https://www.geeksforgeeks.org/python-dictionary-to-list-of-tuple-conversion/)

数据类型之间的相互转换是一个有很多用例的问题，也是更大问题中需要解决的常见子问题。元组到字典的转换之前已经讨论过了。本文讨论了一种相反的情况，即把字典转换成元组列表来表示问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+元组+ `items()`**
这个问题可以通过使用列表理解来构建列表来解决，元组是通过在元组中手动插入键来构建的，items 函数用于以元组的形式获取字典的项键和值。

```py
# Python3 code to demonstrate
# Dictionary to list of tuple conversion
# using list comprehension + tuple + items()

# initializing Dictionary
test_dict = {"Nikhil" : (22, "JIIT"), "Akshat" : (21, "JIIT")} 

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# using list comprehension + tuple + items()
# Dictionary to list of tuple conversion
res = [(key, i, j) for key, (i, j) in test_dict.items()]

# print result
print("The list after conversion : " + str(res))
```

**Output :**

```py
The original dictionary : {'Nikhil': (22, 'JIIT'), 'Akshat': (21, 'JIIT')}
The list after conversion : [('Nikhil', 22, 'JIIT'), ('Akshat', 21, 'JIIT')]

```