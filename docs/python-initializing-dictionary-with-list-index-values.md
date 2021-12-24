# Python |用列表索引值初始化字典

> 原文:[https://www . geesforgeks . org/python-initialization-dictionary-with-list-index-values/](https://www.geeksforgeeks.org/python-initializing-dictionary-with-list-index-values/)

在使用字典时，我们可能会遇到这样一个问题，即我们需要将列表中的每个值都附加上索引，以便以后用来解决问题。这种技术在竞争性编程领域通常非常有用。让我们讨论执行这项任务的某些方法。

**方法#1:利用字典理解和`enumerate()`**
以上方法的组合可以实现这个任务。在这种情况下，enumerate()用其索引迭代值的内在能力被用来使用字典理解来构造对应值的键。

```
# Python3 code to demonstrate working of
# Initializing dictionary with index value
# Using dictionary comprehension and enumerate()

# Initialize list
test_list = ['gfg', 'is', 'best', 'for', 'CS']

# Printing original list 
print("The original list is : " + str(test_list))

# using dictionary comprehension and enumerate()
# Initializing dictionary with index value
res = {key: val for val, key in enumerate(test_list)}

# printing result 
print("Constructed dictionary with index value : " + str(res))
```

**Output :**

```
The original list is : ['gfg', 'is', 'best', 'for', 'CS']
Constructed dictionary with index value : {'gfg': 0, 'is': 1, 'best': 2, 'CS': 4, 'for': 3}

```