# Python–字典中的内部嵌套值列表平均值

> 原文:[https://www . geesforgeks . org/python-内部-嵌套-值-列表-字典中的含义/](https://www.geeksforgeeks.org/python-inner-nested-value-list-mean-in-dictionary/)

有时，在使用 Python Dictionaries 时，我们可能会遇到一个问题，需要提取字典中嵌套值列表的平均值。这个问题可以应用于许多领域，包括网络开发和竞争性编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用`mean() + loop`**
以上功能的组合提供了解决这个问题的蛮力方式。在本文中，我们使用内置的 mean()库执行求平均值的任务，并使用循环迭代嵌套。

```py
# Python3 code to demonstrate working of 
# Inner Nested Value List Mean in Dictionary
# Using mean() + loop
from statistics import mean

# initializing dictionary
test_dict = {'Gfg' : {'a' : [1, 5, 6, 7], 'b' : [6, 7, 8, 9]}, 'is' : {'best' :[2, 8, 9, 0]}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Inner Nested Value List Mean in Dictionary
# Using mean() + loop
for sub in test_dict.values():
    for key in sub:
        sub[key] = mean(sub[key])

# printing result 
print("The modified dictionary : " + str(test_dict)) 
```

**Output :**

> 原词典:{'Gfg': {'a': [1，5，6，7]，' b': [6，7，8，9]}，' is': {'best': [2，8，9，0]}
> 修改后的词典:{'Gfg': {'a': 4.75，' b': 7.5}，' is': {'best': 4.75}}