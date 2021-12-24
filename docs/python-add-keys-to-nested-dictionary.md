# Python |向嵌套字典添加键

> 原文:[https://www . geesforgeks . org/python-向嵌套字典添加键/](https://www.geeksforgeeks.org/python-add-keys-to-nested-dictionary/)

在字典中添加关键字已经讨论过很多次了，但是有时候，我们可能会遇到一个问题，我们需要在嵌套字典中更改/添加关键字。随着 NoSQL 数据库的出现，这类问题在当今世界很常见。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用字典括号**
这个任务可以很容易地使用简单的方法来执行，只需不断地用新值嵌套字典括号，并在移动中创建新键，然后更新字典。

```
# Python3 code to demonstrate working of
# Update nested dictionary keys
# Using dictionary brackets

# initializing dictionary
test_dict = {'GFG' : {'rate' : 4, 'since' : 2012}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using dictionary brackets
# Update nested dictionary keys
test_dict['GFG']['rank'] = 1

# printing result 
print("Dictionary after nested key update : " + str(test_dict))
```

**Output :**

```
The original dictionary is : {'GFG': {'rate': 4, 'since': 2012}}
Dictionary after nested key update : {'GFG': {'rate': 4, 'since': 2012, 'rank': 1}}

```