# Python–将列表列表转换为元组的元组

> 原文:[https://www . geesforgeks . org/python-convert-list-list-to-tuple-of-tuple/](https://www.geeksforgeeks.org/python-convert-list-of-lists-to-tuple-of-tuples/)

有时，在使用 Python 数据时，我们可能会遇到一个问题，即我们需要执行数据类型的相互转换。这种问题可能发生在我们需要以特定格式获取数据的领域，例如机器学习。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [['Best']，['Gfg']，['Gfg']]
> **输出**:(' Best '，)，(' Gfg '，)，(' Gfg '，)
> 
> **输入** : test_list = [['Gfg '，' is '，' Best']]
> **输出**:(' Gfg '，' is '，' Best ')，)

**方法一:使用`tuple()` +列表理解**
以上功能的组合可以解决这个问题。在本例中，我们使用 tuple()执行转换，列表理解用于将逻辑扩展到所有容器。

```py
# Python3 code to demonstrate working of 
# Convert List of Lists to Tuple of Tuples
# Using tuple + list comprehension

# initializing list
test_list = [['Gfg', 'is', 'Best'], ['Gfg', 'is', 'love'],
                            ['Gfg', 'is', 'for', 'Geeks']]

# printing original list
print("The original list is : " + str(test_list))

# Convert List of Lists to Tuple of Tuples
# Using tuple + list comprehension
res = tuple(tuple(sub) for sub in test_list)

# printing result 
print("The converted data : " + str(res)) 
```

**Output :**

> 原列表为:[['Gfg '，' is '，' Best']，['Gfg '，' is '，' love']，['Gfg '，' is '，' for '，' Geeks']]
> 转换后的数据:(' Gfg '，' is '，' Best ')，(' Gfg '，' is '，' for '，' Geeks ')

**方法 2:使用`map() + tuple()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 map()执行使用列表理解执行的任务，以将转换逻辑扩展到每个子列表。

```py
# Python3 code to demonstrate working of 
# Convert List of Lists to Tuple of Tuples
# Using map() + tuple()

# initializing list
test_list = [['Gfg', 'is', 'Best'], ['Gfg', 'is', 'love'],
                             ['Gfg', 'is', 'for', 'Geeks']]

# printing original list
print("The original list is : " + str(test_list))

# Convert List of Lists to Tuple of Tuples
# Using map() + tuple()
res = tuple(map(tuple, test_list))

# printing result 
print("The converted data : " + str(res)) 
```

**Output :**

> 原列表为:[['Gfg '，' is '，' Best']，['Gfg '，' is '，' love']，['Gfg '，' is '，' for '，' Geeks']]
> 转换后的数据:(' Gfg '，' is '，' Best ')，(' Gfg '，' is '，' for '，' Geeks ')