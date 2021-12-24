# Python–将记录列表转换为隔离字典

> 原文:[https://www . geesforgeks . org/python-convert-records-list-to-separated-dictionary/](https://www.geeksforgeeks.org/python-convert-records-list-to-segregated-dictionary/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要将元组记录的每个元素转换为字典中的一个单独的键，每个索引都有不同的值。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是解决这个问题的方法之一。在这种情况下，我们迭代元组列表，并为新构造的字典的每个键分配所需的值。

```py
# Python3 code to demonstrate working of 
# Convert Records List to Segregated Dictionary
# Using loop

# initializing list
test_list = [(1, 2), (3, 4), (5, 6)]

# printing original list
print("The original list is : " + str(test_list))

# initializing index value
frst_idx = "Gfg"
scnd_idx = 'best'

# Convert Records List to Segregated Dictionary
# Using loop
res = dict()
for sub in test_list:
    res[sub[0]] = frst_idx
    res[sub[1]] = scnd_idx

# printing result 
print("The constructed Dictionary list : " + str(res)) 
```

**Output :**

> 原始列表为:[(1，2)，(3，4)，(5，6)]
> 构建的字典列表:{1: 'Gfg '，2: 'best '，3: 'Gfg '，4: 'best '，5: 'Gfg '，6: 'best'}