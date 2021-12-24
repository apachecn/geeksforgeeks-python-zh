# Python |连接字典值列表

> 原文:[https://www . geesforgeks . org/python-concatenate-dictionary-value-list/](https://www.geeksforgeeks.org/python-concatenate-dictionary-value-lists/)

有时候，在使用字典时，我们可能会遇到一个问题，即我们有列表作为它的值，并希望通过串联将它累积在单个列表中。这个问题可能发生在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum() + values()`**
这是执行此任务最推荐的方法和一个内胆。在本例中，我们使用`values()`访问所有列表值，并使用`sum()`执行连接实用程序。

```
# Python3 code to demonstrate working of
# Concatenating dictionary value lists
# Using sum() + values()

# initializing dictionary
test_dict = {"Gfg" : [4, 5], "is" : [6, 8], "best" : [10]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Concatenating dictionary value lists
# Using sum() + values()
res = sum(test_dict.values(), [])

# printing result 
print("The Concatenated list values are : " + str(res))
```

**Output :**

```
The original dictionary is : {'Gfg': [4, 5], 'best': [10], 'is': [6, 8]}
The Concatenated list values are : [4, 5, 10, 6, 8]

```