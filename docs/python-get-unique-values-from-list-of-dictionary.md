# Python |从字典列表中获取唯一值

> 原文:[https://www . geesforgeks . org/python-从字典列表中获取唯一值/](https://www.geeksforgeeks.org/python-get-unique-values-from-list-of-dictionary/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们需要在一个列表中找到所有字典的唯一值。这种实用程序可能会在处理类似数据时出现，我们希望提取唯一的数据。让我们讨论执行这项任务的某些方法。

**方法#1:使用`set() + values()` +字典理解**
这些方法的组合可以共同帮助我们实现获得唯一值的任务。values 函数帮助我们获取字典的值，set 帮助我们获取它们的唯一性，以及字典理解来遍历列表。

```
# Python3 code to demonstrate working of
# Get Unique values from list of dictionary
# Using set() + values() + dictionary comprehension

# Initialize list 
test_list = [{'gfg' : 1, 'is' : 2}, {'best' : 1, 'for' : 3}, {'CS' : 2}]

# printing original list
print("The original list : " +  str(test_list))

# Using set() + values() + dictionary comprehension
# Get Unique values from list of dictionary
res = list(set(val for dic in test_list for val in dic.values()))

# printing result 
print("The unique values in list are : " + str(res))
```

**Output :**

> 原始列表:[{'gfg': 1，' is': 2}，{'best': 1，' for': 3}，{'CS': 2}]
> 列表中的唯一值为:[1，2，3]