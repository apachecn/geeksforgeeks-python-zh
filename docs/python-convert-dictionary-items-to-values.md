# Python–将字典项目转换为值

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-items-to-values/](https://www.geeksforgeeks.org/python-convert-dictionary-items-to-values/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要将字典的所有项目转换为单独的值字典。这个问题可能发生在我们接收字典的应用程序中，其中键和值都需要映射为单独的值。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'Gfg': 1}
> **输出** : [{'key': 'Gfg '，' value': 1}]
> 
> **输入** : test_dict = {'Gfg': 1，' best': 5}
> **输出** : [{'key': 'Gfg '，' value': 1}，{'key': 'best '，' value': 5}]

**方法#1:使用循环**
这是蛮力的方式解决这个问题。在这种情况下，我们需要运行一个循环来为字典的每个条目分配不同的值。

```
# Python3 code to demonstrate working of 
# Convert dictionary items to values
# Using loop

# initializing dictionary
test_dict = {'Gfg': 1, 'is': 2, 'best': 3}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Convert dictionary items to values
# Using loop
res = []
for key, val in test_dict.items():
    res.append({"key": key, "value": val})

# printing result 
print("Converted Dictionary : " + str(res)) 
```

**Output :**

> 原始字典:{'Gfg': 1，' is': 2，' best': 3}
> 转换字典:[{'key': 'Gfg '，' value': 1}，{'key': 'is '，' value': 2}，{'key': 'best '，' value': 3}]

**方法 2:使用列表理解**
这是另一种可以执行该任务的方式。这以与上面类似的方式解决了问题，但是以速记的形式是一种更紧凑的方式。

```
# Python3 code to demonstrate working of 
# Convert dictionary items to values
# Using list comprehension

# initializing dictionary
test_dict = {'Gfg': 1, 'is': 2, 'best': 3}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Convert dictionary items to values
# Using list comprehension
res = [{'key': key, 'value': test_dict[key]} for key in test_dict]

# printing result 
print("Converted Dictionary : " + str(res)) 
```

**Output :**

> 原始字典:{'Gfg': 1，' is': 2，' best': 3}
> 转换字典:[{'key': 'Gfg '，' value': 1}，{'key': 'is '，' value': 2}，{'key': 'best '，' value': 3}]