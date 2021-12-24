# Python |从字典中获取所有元组键

> 原文:[https://www . geesforgeks . org/python-get-all-tuple-key-from-dictionary/](https://www.geeksforgeeks.org/python-get-all-tuple-keys-from-dictionary/)

有时，在使用 Python 字典时，我们可以使用元组形式的键。一个元组中可以有许多元素，有时，获取这些元素是非常必要的。如果它们是字典关键字的一部分，并且我们希望获得所有元组关键字元素，我们需要执行某些功能来实现这一点。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
在这个方法中，我们只需遍历每个字典条目，并将其关键元素放入列表中。

```py
# Python3 code to demonstrate working of
# Get all tuple keys from dictionary
# Using list comprehension

# Initializing dict
test_dict = {(5, 6) : 'gfg', (1, 2, 8) : 'is', (9, 10) : 'best'}

# printing original dict
print("The original dict is : " + str(test_dict))

# Get all tuple keys from dictionary
# Using list comprehension
res = [ele for key in test_dict for ele in key]

# printing result
print("The dictionary tuple key elements are : " + str(res))
```

**Output :**

```py
The original dict is : {(5, 6): 'gfg', (9, 10): 'best', (1, 2, 8): 'is'}
The dictionary tuple key elements are : [5, 6, 9, 10, 1, 2, 8]

```