# Python–将字典值列表提取到列表中

> 原文:[https://www . geesforgeks . org/python-extract-dictionary-values-list-to-list/](https://www.geeksforgeeks.org/python-extract-dictionary-values-list-to-list/)

有时，在处理字典记录时，我们可能会遇到需要将所有字典值提取到一个单独列表中的问题。这在数据领域和网络开发中可能有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`map()` +生成器表达式**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用生成器表达式执行值提取任务，并使用 map()重建值列表。

```
# Python3 code to demonstrate working of 
# Extracting Dictionary values list to List
# Using map() + generator expression

# initializing dictionary
test_dict = {'gfg' : [4, 6, 7, 8],
             'is' : [3, 8, 4, 2, 1],
             'best' : [9, 5, 2, 1, 0]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Extracting Dictionary values to List
# Using map() + generator expression
res = list(map(list, (ele for ele in test_dict.values())))

# printing result 
print("The list of dictionary values : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': [3，8，4，2，1]，' gfg': [4，6，7，8]，' best': [9，5，2，1，0]}
> 字典值列表:[[3，8，4，2，1]，[4，6，7，8]，[9，5，2，1，0]]