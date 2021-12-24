# Python |字典组合键

> 原文:[https://www . geesforgeks . org/python-dictionary-key-组合键/](https://www.geeksforgeeks.org/python-dictionary-key-combinations/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要获取字典对的所有可能的对组合。这种应用可以出现在数据科学领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `enumerate()`**
在该方法中，我们只需通过列表理解迭代字典，构造成对的键并插入新的列表。枚举函数用于通过访问索引将关键元素绑定在一起。

```
# Python3 code to demonstrate working of
# Dictionary key combinations
# Using list comprehension + enumerate()

# Initializing dict
test_dict = {'gfg' : 1, 'is' : 2, 'the' : 3, 'best' : 4}

# printing original dict
print("The original dict is : " + str(test_dict))

# Dictionary key combinations
# Using list comprehension + enumerate()
test_dict = list(test_dict)
res = [(x, y) for idx, x in enumerate(test_dict) for y in test_dict[idx + 1: ]]

# printing result
print("The dictionary key pair list is : " + str(res))
```

**Output :**

```
The original dict is : {'is': 2, 'the': 3, 'best': 4, 'gfg': 1}
The dictionary key pair list is : [('is', 'the'), ('is', 'best'), ('is', 'gfg'), ('the', 'best'), ('the', 'gfg'), ('best', 'gfg')]

```