# Python–将值列表元素转换为列表记录

> 原文:[https://www . geesforgeks . org/python-convert-value-list-elements-to-list-records/](https://www.geeksforgeeks.org/python-convert-value-list-elements-to-list-records/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们需要将嵌套列表值转换为单个记录，以包含另一个层次的嵌套来容纳数据。这种问题可以应用于数据领域，如网络开发和机器学习。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'gfg' : [4，5]，' best' : [8，10，7，9]}
> **输出** : {'best': [{8: []}，{10: []}，{7: []}，{9: []}]，' gfg': [{4: []}，{5: []}]
> 
> **输入**:test _ dict = { ' gfg ':[7]}
> **输出** : {'gfg': [{7: []}]}

**方法#1:使用 loop + `enumerate()`**
以上功能的组合可以用来解决这个问题。这是一种蛮力方法，我们迭代所有列表，并为每个值创建记录列表。

```py
# Python3 code to demonstrate working of 
# Convert Value list elements to List records
# Using loop + enumerate()

# initializing dictionary
test_dict = {'gfg' : [4, 5], 'is' : [8], 'best' : [10]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Convert Value list elements to List records
# Using loop + enumerate()
for ele in test_dict.values():
    for idx, val in enumerate(ele):
        ele[idx] = {val: []}

# printing result 
print("The converted dictionary is : " + str(test_dict)) 
```

**Output :**

> 原始字典:{'best': [10]，' is': [8]，' gfg': [4，5]}
> 转换后的字典为:{'best': [{10: []}]，' is': [{8: []}]，' gfg': [{4: []}，{5: []}]}

**方法二:利用字典理解+ `items()`**
这是解决这个问题的速记方法。在这种情况下，使用字典理解创建字典，并使用条目()提取字典条目。

```py
# Python3 code to demonstrate working of 
# Convert Value list elements to List records
# Using dictionary comprehension + items()

# initializing dictionary
test_dict = {'gfg' : [4, 5], 'is' : [8], 'best' : [10]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Convert Value list elements to List records
# Using dictionary comprehension + items()
res = {key: [{val: []} for val in sub] for key, sub in test_dict.items()}

# printing result 
print("The converted dictionary is : " + str(res)) 
```

**Output :**

> 原始字典:{'best': [10]，' is': [8]，' gfg': [4，5]}
> 转换后的字典为:{'best': [{10: []}]，' is': [{8: []}]，' gfg': [{4: []}，{5: []}]}