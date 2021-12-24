# Python–字典中不等项的出现频率

> 原文:[https://www . geeksforgeeks . org/python-字典中出现不等项的频率/](https://www.geeksforgeeks.org/python-frequency-of-unequal-items-in-dictionary/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要检查两个字典之间的项目计数是否不相等。这在 web 开发和其他领域也有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用字典理解**
这个特殊的任务可以使用字典理解在一行中执行，字典理解提供了一种压缩冗长的野蛮逻辑的方法，并且只检查不相等的项目和增量计数。

```py
# Python3 code to demonstrate working of
# Dissimilar items frequency in Dictionary
# Using dictionary comprehension

# initializing dictionaries
test_dict1 = {'gfg' : 1, 'is' : 2, 'best' : 3}
test_dict2 = {'gfg' : 1, 'is' : 2, 'good' : 3}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Dissimilar items frequency in Dictionary
# Using dictionary comprehension
res = {key: test_dict1[key] for key in test_dict1 if key not in test_dict2}

# printing result
print("The number of uncommon items are : " + str(len(res)))
```

**Output :**

```py
The original dictionary 1 is : {'best': 3, 'is': 2, 'gfg': 1}
The original dictionary 2 is : {'good': 3, 'is': 2, 'gfg': 1}
The number of uncommon items are : 1

```