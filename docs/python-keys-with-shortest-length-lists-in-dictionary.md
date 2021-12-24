# Python–字典中长度列表最短的键

> 原文:[https://www . geesforgeks . org/python-长度最短的键-字典列表/](https://www.geeksforgeeks.org/python-keys-with-shortest-length-lists-in-dictionary/)

有时，在使用 Python 列表时，我们可能会遇到这样的问题，即需要将列表长度最小的键作为值返回。这可以应用于我们处理数据的领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用`len() + loop + items()`**
上述功能的组合可用于执行该任务。在这种情况下，我们迭代字典的键，并使用 len()返回所有长度等于最小列表长度的键。

```py
# Python3 code to demonstrate working of 
# Keys with shortest length lists in dictionary
# Using len() + loop + items()

# initializing dictionary
test_dict = {'gfg' : [4, 5],
             'is' : [9, 7, 3, 10],
             'best' : [11, 34],
             'for' : [6, 8, 2], 
             'geeks' : [12, 24]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Keys with shortest length lists in dictionary
# Using len() + loop + items()
min_val = min([len(test_dict[ele]) for ele in test_dict])
res = []
for ele in test_dict:
    if len(test_dict[ele]) == min_val:
        res.append(ele)

# printing result 
print("The required keys are : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': [9，7，3，10]，' gfg': [4，5]，' best': [11，34]，' for': [6，8，2]，' geeks': [12，24]}
> 所需的键为:['gfg '，' best '，' geeks']