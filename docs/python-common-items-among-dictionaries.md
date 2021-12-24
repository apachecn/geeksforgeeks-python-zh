# Python |词典间常用项

> 原文:[https://www . geeksforgeeks . org/python-字典中的常见项目/](https://www.geeksforgeeks.org/python-common-items-among-dictionaries/)

有时，在使用 Python 时，我们会遇到一个问题，即我们需要检查两个字典中相等的项目数。这在 web 开发和其他领域也有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用字典理解**
这个特殊的任务可以使用字典理解在一行中执行，字典理解提供了一种压缩冗长的野蛮逻辑的方法，并且只检查相等的项目和增量计数。

```
# Python3 code to demonstrate the working of
# Equal items among dictionaries
# Using dictionary comprehension

# initializing dictionaries
test_dict1 = {'gfg' : 1, 'is' : 2, 'best' : 3}
test_dict2 = {'gfg' : 1, 'is' : 2, 'good' : 3}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Equal items among dictionaries
# Using dictionary comprehension
res =  {key: test_dict1[key] for key in test_dict1 if 
        key in test_dict2 and test_dict1[key] == test_dict2[key]}

# printing result
print("The number of common items are : " + str(len(res)))
```

**Output :**

```
The original dictionary 1 is : {'gfg': 1, 'best': 3, 'is': 2}
The original dictionary 2 is : {'gfg': 1, 'is': 2, 'good': 3}
The number of common items are : 2

```