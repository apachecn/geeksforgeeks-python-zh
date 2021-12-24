# Python–提取具有最大元组值的项目

> 原文:[https://www . geesforgeks . org/python-extract-item-with-maximum-tuple-value/](https://www.geeksforgeeks.org/python-extract-item-with-maximum-tuple-value/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即需要提取值元组索引值最大的项。这种问题在 web 开发等领域都有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'gfg' : (4，6)，' is' : (7，8)，' best' : (8，2)}，tup_idx = 0
> **输出** : ('best '，(8，2))
> 
> **输入** : test_dict = {'gfg' : (4，6)，' best' : (8，2)}，tup_idx = 1
> **输出** : ('gfg' : (4，6))

**方法#1:使用 `max() + lambda`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 max 执行提取最大项目的任务，并使用 lambda 检查 value 参数。

```py
# Python3 code to demonstrate working of 
# Extract Item with Maximum Tuple Value
# Using max() + lambda

# initializing dictionary
test_dict = {'gfg' : (4, 6),
             'is' : (7, 8),
             'best' : (8, 2)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing tuple index 
# 0 based indexing
tup_idx = 1

# Extract Item with Maximum Tuple Value
# Using max() + lambda
res = max(test_dict.items(), key = lambda ele: ele[1][tup_idx])

# printing result 
print("The extracted maximum element item : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'gfg': (4, 6), 'is': (7, 8), 'best': (8, 2)}
The extracted maximum element item : ('is', (7, 8))

```

**方法 2:使用`max() + map() + itemgetter() + zip()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 zip()执行使用 itemgetter()提取关键字和所需元组索引值的任务。然后使用 max()提取最大元素。

```py
# Python3 code to demonstrate working of 
# Extract Item with Maximum Tuple Value
# Using max() + map() + itemgetter() + zip()
from operator import itemgetter

# initializing dictionary
test_dict = {'gfg' : (4, 6),
             'is' : (7, 8),
             'best' : (8, 2)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing tuple index 
# 0 based indexing
tup_idx = 1

# Extract Item with Maximum Tuple Value
# Using max() + map() + itemgetter() + zip()
res = max(zip(test_dict.keys(), map(itemgetter(tup_idx), inventory.values())), key = itemgetter(1))[0]
res = (res, test_dict[res])

# printing result 
print("The extracted maximum element item : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'gfg': (4, 6), 'is': (7, 8), 'best': (8, 2)}
The extracted maximum element item : ('is', (7, 8))

```