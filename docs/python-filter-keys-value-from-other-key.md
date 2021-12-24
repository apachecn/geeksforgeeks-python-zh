# Python–从其他键中过滤键的值

> 原文:[https://www . geesforgeks . org/python-filter-key-value-from-other-key/](https://www.geeksforgeeks.org/python-filter-keys-value-from-other-key/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们需要在其他一些键相等的基础上从键的字典列表中提取一个值。这种问题在包含数据的领域很常见，例如网络开发。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list = [{'gfg' : 5，' is' : 8，' best' : 24}，{'gfg' : 7，' is' : 12，' best ':24 }]
> req _ Key = ' gfg '[Requested Key]
> fil _ Key = ' best '[filing Key]
> fil _ val = 24[过滤值待查]
> **输出** : [5，7]
> 
> **输入** :
> test_list = [{'gfg' : 5，' is' : 8，' best ':24 }]
> req _ Key = ' gfg '[Requested Key]
> fil _ Key = ' best '[filting Key]
> fil _ val = 24[待检查的过滤值]
> **输出** : [5]

**方法#1:使用循环**
这是蛮力的方式解决这个问题。在这种情况下，我们手动迭代整个列表并检查过滤器关键字的值，在相等的情况下，我们提取所需关键字的值。

```py
# Python3 code to demonstrate working of 
# Filter key's value from other key
# Using loop

# initializing list
test_list = [{'gfg' : 5, 'is' : 8, 'best' : 12}, 
             {'gfg' : 7, 'is' : 12, 'best' : 24},
             {'gfg' : 20, 'is' : 17, 'best' : 18}]

# printing original list
print("The original list is : " + str(test_list))

# initializing required key
req_key = 'gfg'

# initializing filter key
fil_key = 'best'

# initializing filter val 
fil_val = 24

# Filter key's value from other key
# Using loop
res = []
for sub in test_list:
  if sub[fil_key] == fil_val:
    res.append(sub[req_key])

# printing result 
print("The required value : " + str(res)) 
```

**Output :**

> 原始列表为:[{'gfg': 5，' is': 8，' best': 12}，{'gfg': 7，' is': 12，' best': 24}，{'gfg': 20，' is': 17，' best': 18}]
> 所需值:[7]

**方法 2:使用列表理解**
这是解决这个问题的又一种方法。在这种情况下，我们使用列表理解结构以速记方式执行与上述方法类似的任务。

```py
# Python3 code to demonstrate working of 
# Filter key's value from other key
# Using list comprehension

# initializing list
test_list = [{'gfg' : 5, 'is' : 8, 'best' : 12}, 
             {'gfg' : 7, 'is' : 12, 'best' : 24},
             {'gfg' : 20, 'is' : 17, 'best' : 18}]

# printing original list
print("The original list is : " + str(test_list))

# initializing required key
req_key = 'gfg'

# initializing filter key
fil_key = 'best'

# initializing filter val 
fil_val = 24

# Filter key's value from other key
# Using list comprehension
res = [sub[req_key] for sub in test_list if sub[fil_key] == fil_val]

# printing result 
print("The required value : " + str(res)) 
```

**Output :**

> 原始列表为:[{'gfg': 5，' is': 8，' best': 12}，{'gfg': 7，' is': 12，' best': 24}，{'gfg': 20，' is': 17，' best': 18}]
> 所需值:[7]