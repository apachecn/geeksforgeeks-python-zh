# Python–列表中的自定义字典初始化

> 原文:[https://www . geesforgeks . org/python-custom-dictionary-initialization-in-list/](https://www.geeksforgeeks.org/python-custom-dictionary-initialization-in-list/)

在使用 Python 时，我们可能会遇到一个问题，那就是我们需要用自定义字典初始化一个特定大小的列表。这个任务在 web 开发中存储记录很有用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`{dict} + "*" operator`**
该任务可以使用“*”运算符执行。我们可以创建一个包含单个自定义字典的列表，然后将其乘以列表大小的数字。缺点是将制作指向相似存储位置的相似参考字典。

```
# Python3 code to demonstrate working of
# Custom dictionary initialization in list
# using {dict} + "*" operator

# Initialize dict 
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# Custom dictionary initialization in list
# using {dict} + "*" operator
res = [test_dict] * 6

print("The list of custom dictionaries is : " + str(res))
```

**Output :**

```
The list of custom dictionaries is : [{'gfg': 1, 'best': 3, 'is': 2}, {'gfg': 1, 'best': 3, 'is': 2}, {'gfg': 1, 'best': 3, 'is': 2}, {'gfg': 1, 'best': 3, 'is': 2}, {'gfg': 1, 'best': 3, 'is': 2}, {'gfg': 1, 'best': 3, 'is': 2}]

```