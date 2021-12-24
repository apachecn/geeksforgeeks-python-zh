# Python–所有可能的项目组合词典

> 原文:[https://www . geesforgeks . org/python-所有可能的项目-组合-字典/](https://www.geeksforgeeks.org/python-all-possible-items-combination-dictionary/)

有时，在处理数据时，我们可能会遇到一个问题，即我们获得了键和值列表的样本数据，并且我们要求将实际数据构建为大小相似的键和值列表的所有可能组合。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `set()`**
上述功能的组合可以用来解决这个问题。在这种情况下，我们首先提取集合列表中展平的所有项目。然后我们用集合减法构造每个字典。

```
# Python3 code to demonstrate working of 
# All possible items combination dictionary
# Using loop + set()

# initializing Dictionary
test_dict = {'gfg' : [1, 3], 'is' : [5, 6], 'best' : [4, 7]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# All possible items combination dictionary
# Using loop + set()
temp = [set([key]) | set(value) for key, value in test_dict.items() ]
res = {}
for sub in temp:
    for key in sub:
        res[key] = list(sub - set([key]))

# printing result 
print("The all possible items dictionary : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': [5，6]，' gfg': [1，3]，' best': [4，7]}
> 所有可能的项目字典:{1: [3，' gfg']，3: [1，' gfg']，4: ['best '，7]，5: ['is '，6]，6: ['is '，5]，7: [4，' best']，' best': [4，7]，' is': [5，6]，' gfg': [1，3]}