# Python–将平面词典转换为嵌套词典

> 原文:[https://www . geesforgeks . org/python-convert-flat-dictionary-to-nested-dictionary/](https://www.geeksforgeeks.org/python-convert-flat-dictionaries-to-nested-dictionary/)

有时，在处理记录时，我们可能会遇到这样的问题:我们需要执行将多个平面字典转换为单个嵌套字典的任务。这可以在许多广泛使用数据的领域中得到应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`dict()` +键访问**
这是可以执行该任务的方式之一。在这种情况下，我们使用 dict 构造空字典，并使用手动强力键访问为字典分配一个新的级别。

```py
# Python3 code to demonstrate working of 
# Convert Flat dictionaries to Nested dictionary
# Using key access + dict()

# initializing dictionaries
test_dict1 = {'gfg' : 1, 'best' : 2}
test_dict2 = {'for' : 3, 'geeks' : 5}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Convert Flat dictionaries to Nested dictionary
# Using key access + dict()
res = dict()
res["level1"] = test_dict1
res['level2'] = test_dict2

# printing result 
print("The nested dictionary is : " + str(res)) 
```

**Output :**

> 原始字典 1 为:{'gfg': 1，' best': 2}
> 原始字典 2 为:{'geeks': 5，' for': 3}
> 嵌套字典为:{'level2': {'geeks': 5，' for': 3}，' level1': {'gfg': 1，' best': 2}}