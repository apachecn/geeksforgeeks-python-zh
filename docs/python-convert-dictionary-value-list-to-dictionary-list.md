# Python–将字典值列表转换为字典列表

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-value-list-to-dictionary-list/](https://www.geeksforgeeks.org/python-convert-dictionary-value-list-to-dictionary-list/)

有时候，在使用 Python Dictionaries 时，我们可能会遇到一个问题，即需要将字典列表转换为嵌套记录字典，获取字典列表值的每个索引并将其展平。这种问题在许多领域都有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'Gfg': [5，6]}，{'best': [3，1]}]
> **输出** : [{'Gfg': 5，' best': 3}，{'Gfg': 6，' best': 1}]
> 
> **输入**:test _ list =[{ ' Gfg ':[5]}]
> **输出** : [{'Gfg': 5}]

**方法#1:使用循环**
这是解决这个问题的方法之一。在这种情况下，我们以强力方式执行任务，迭代每个列表值索引，并为其指定一个键。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Dictionary Value list to Dictionary List
# Using loop

# initializing list
test_list = [{'Gfg' : [5, 6, 5]}, {'is' : [10, 2, 3]}, {'best' : [4, 3, 1]}]

# printing original list
print("The original list is : " + str(test_list))

# Convert Dictionary Value list to Dictionary List
# Using loop
res =[{} for idx in range(len(test_list))]
idx = 0
for sub in test_list:
    for key, val in sub.items():
        for ele in val:
            res[idx][key] = ele
            idx += 1
        idx = 0

# printing result
print("Records after conversion : " + str(res))
```

**Output : **The original list is : [{‘Gfg’: [5, 6, 5]}, {‘is’: [10, 2, 3]}, {‘best’: [4, 3, 1]}] Records after conversion : [{‘Gfg’: 5, ‘is’: 10, ‘best’: 4}, {‘Gfg’: 6, ‘is’: 2, ‘best’: 3}, {‘Gfg’: 5, ‘is’: 3, ‘best’: 1}]  

**方法 2:使用列表理解+ zip()**
这是我们执行这项任务的又一种方式。在这种情况下，我们分两步执行任务，首先，我们提取所有的键，然后相应地使用 zip()对值进行配对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Dictionary Value list to Dictionary List
# Using list comprehension + zip()

# initializing list
test_list = [{'Gfg' : [5, 6, 5]}, {'is' : [10, 2, 3]}, {'best' : [4, 3, 1]}]

# printing original list
print("The original list is : " + str(test_list))

# Convert Dictionary Value list to Dictionary List
# Using list comprehension + zip()
keys = [list(sub.keys())[0] for sub in test_list]
vals = zip(*[val for sub in test_list for val in sub.values()])
res = [dict(zip(keys, val)) for val in vals]

# printing result
print("Records after conversion : " + str(res))
```

**Output : **The original list is : [{‘Gfg’: [5, 6, 5]}, {‘is’: [10, 2, 3]}, {‘best’: [4, 3, 1]}] Records after conversion : [{‘Gfg’: 5, ‘is’: 10, ‘best’: 4}, {‘Gfg’: 6, ‘is’: 2, ‘best’: 3}, {‘Gfg’: 5, ‘is’: 3, ‘best’: 1}]