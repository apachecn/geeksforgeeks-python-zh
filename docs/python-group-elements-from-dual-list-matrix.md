# Python–将双列表矩阵中的元素分组

> 原文:[https://www . geesforgeks . org/python-group-elements-from-dual-list-matrix/](https://www.geeksforgeeks.org/python-group-elements-from-dual-list-matrix/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要将列表中的元素与矩阵的第一个元素分组，并以字典的形式执行分组。这在许多领域都有优势。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+列表理解**
以上方法的组合可用于执行此任务。在这种情况下，我们遍历对偶元素行，并使用来自列表的元素和对偶行矩阵的第二列的映射来计算字典。

```
# Python3 code to demonstrate 
# Group elements from Dual List Matrix
# using loop + list comprehension

# Initializing lists
test_list1 = ['Gfg', 'is', 'best']
test_list2 = [['Gfg', 1], ['is', 2], ['best', 1], ['Gfg', 4], ['is', 8], ['Gfg', 7]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Group elements from Dual List Matrix
# using loop + list comprehension
res = {key: [] for key in test_list1}
for key in res:
    res[key] = [sub[1] for sub in test_list2 if key == sub[0]]

# printing result 
print ("The dictionary after grouping : " + str(res))
```

**Output :**

> 原列表 1 为:['Gfg '，' is '，' best']
> 原列表 2 为:[['Gfg '，1]，['is '，2]，['best '，1]，['Gfg '，4]，['is '，8]，['Gfg '，7]]
> 分组后的字典:{'is': [2，8]，' Gfg': [1，4，7]，' best': [1]}