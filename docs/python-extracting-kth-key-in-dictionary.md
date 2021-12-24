# Python–提取字典中的第 k 个键

> 原文:[https://www . geesforgeks . org/python-extracting-kth-key-in-dictionary/](https://www.geeksforgeeks.org/python-extracting-kth-key-in-dictionary/)

很多时候，在使用 Python 的时候，我们会有一种情况，我们需要获取字典的 Kth 键。它可以有许多特定的用途，要么用于检查索引，还有更多类似的用途。这对于 Python 版本很有用，在该版本中，键的排序类似于插入排序。让我们讨论执行这项任务的某些方法。

**方法#1:使用`list() + keys()`**
上述方法的组合可用于执行该特定任务。在这种情况下，我们只需将 keys()提取的整个字典的键转换成一个列表，然后只需访问 Kth 键。

```
# Python3 code to demonstrate working of
# Extracting Kth Key in Dictionary
# Using keys() + list()

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 1

# Using keys() + list()
# Extracting Kth Key in Dictionary
res = list(test_dict.keys())[K]

# printing Kth key
print("The Kth key of dictionary is : " + str(res))
```

**Output :**

```
The original dictionary is : {'best': 3, 'Gfg': 1, 'is': 2}
The Kth key of dictionary is : Gfg

```