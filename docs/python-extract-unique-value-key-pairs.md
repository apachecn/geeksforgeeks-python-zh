# Python–提取唯一值密钥对

> 原文:[https://www . geesforgeks . org/python-extract-unique-value-key-pairs/](https://www.geeksforgeeks.org/python-extract-unique-value-key-pairs/)

有时，在处理 Python 字典时，我们会遇到一个问题，即我们需要从字典列表中提取选定的键对，这太独特了。这种问题可以应用于许多领域，包括日常编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'gfg' : 5，' best' : 12}，{'gfg' : 5，' best' : 12}，]
> **输出** : {(5，12)}
> 
> **输入** : test_list = [{'gfg' : 5，' is': 5，' best' : 12}]
> **输出** : {(5，12)}

**方法#1:使用列表理解**
使用上述功能可以解决这个问题。在这种情况下，我们使用条件句和“In”运算符来执行匹配。使用列表理解编译整个逻辑。

```
# Python3 code to demonstrate working of 
# Extract Unique value key pairs
# Using list comprehension

# initializing list
test_list = [{'gfg' : 5, 'is' : 8, 'best' : 12}, 
             {'gfg' : 5, 'is' : 12, 'best' : 12},
             {'gfg' : 20, 'is' : 17, 'best' : 12}]

# printing original list
print("The original list is : " + str(test_list))

# initializing required keys
req_key1 = 'gfg'
req_key2 = 'best'

# Extract Unique value key pairs
# Using list comprehension
res =  {tuple(sub[idx] for idx in [req_key1, req_key2]) for sub in test_list}

# printing result 
print("The required values : " + str(res)) 
```

**Output :**

> 原始列表为:[{'gfg': 5，' is': 8，' best': 12}，{'gfg': 5，' is': 12，' best': 12}，{'gfg': 20，' is': 17，' best': 12}]
> 所需值:{(5，12)，(20，12)}

**方法 2:使用`map() + zip() + itemgetter()`**
上述功能的组合可用于执行该任务。在本例中，我们使用 itemgetter 提取值，使用 zip()组合值，使用 map()将组合结果转换为 set。

```
# Python3 code to demonstrate working of 
# Extract Unique value key pairs
# Using map() + zip() + itemgetter()
from operator import itemgetter

# initializing list
test_list = [{'gfg' : 5, 'is' : 8, 'best' : 12}, 
             {'gfg' : 5, 'is' : 12, 'best' : 12},
             {'gfg' : 15, 'is' : 17, 'best' : 21}]

# printing original list
print("The original list is : " + str(test_list))

# initializing required keys
req_key1 = 'gfg'
req_key2 = 'best'

# Extract Unique value key pairs
# Using map() + zip() + itemgetter()
temp = zip(*map(itemgetter(req_key1, req_key2), test_list))
res = list(map(set, temp))

# printing result 
print("The required values : " + str(res)) 
```

**Output :**

> 原始列表为:[{'gfg': 5，' is': 8，' best': 12}，{'gfg': 5，' is': 12，' best': 12}，{'gfg': 15，' is': 17，' best': 21}]
> 所需值:[{5，15}，{12，21}]