# Python–频率分组字典

> 原文:[https://www . geesforgeks . org/python-frequency-group-dictionary/](https://www.geeksforgeeks.org/python-frequency-grouping-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要对字典数据进行分组，这种方式需要将所有相似的字典按其频率进行分组。这类问题在 web 开发领域有其应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'best': 2，' Gfg': 1}，{'best': 2，' Gfg': 1}]
> **输出** : [{'freq': 2，' Gfg': 1}]
> 
> **输入** : test_list = [{'Gfg': 1，' best': 2}，{'Gfg': 2，' best': 1}]
> **输出** : [{'Gfg': 1，' freq': 1}，{'Gfg': 2，' freq': 1}]

**方法一:使用`defaultdict()` +列表理解**
以上功能的组合可以用来执行此任务。在这种情况下，我们用整数初始化 defaultdict 以获得频率，并使用列表理解来编译结果字典。

```py
# Python3 code to demonstrate working of 
# Frequency Grouping Dictionary
# Using defaultdict() + list comprehension
from collections import defaultdict

# initializing list
test_list = [{'Gfg' :  1, 'best' : 2}, 
             {'Gfg' :  1, 'best' : 2},
             {'Gfg' :  2, 'good' : 3},
             {'Gfg' :  2, 'best' : 2},
             {'Gfg' :  2, 'good' : 3}]

# printing original list
print("The original list is : " + str(test_list))

# Frequency Grouping Dictionary
# Using defaultdict() + list comprehension
temp = defaultdict(int)
for sub in test_list:
    key = sub['Gfg']
    temp[key] += 1

res = [{"Gfg": key, "freq": val} for (key, val) in temp.items()]

# printing result 
print("The frequency dictionary : " + str(res)) 
```

**Output :**

> 原始列表为:[{'Gfg': 1，' best': 2}，{'Gfg': 1，' best': 2}，{'good': 3，' Gfg': 2}，{'Gfg': 2 }，{'good': 3，' Gfg': 2}]
> 频率字典:[{'Gfg': 1，' freq': 2}，{ ' Gfg ':2，' freq': 3}]