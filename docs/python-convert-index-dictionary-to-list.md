# Python–将索引字典转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-index-dictionary-to-list/](https://www.geeksforgeeks.org/python-convert-index-dictionary-to-list/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即键与值映射，其中键表示必须放置值的列表索引。这种问题可以应用于所有数据领域，例如 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = { 1 : 'Gfg '，3 : 'is '，5 : 'Best' }
> **输出** : [0，' Gfg '，0，' is '，0，' Best '，0，0，0，0，0，0]
> 
> **输入** : test_dict = { 2 : 'Gfg '，6 : 'Best' }
> **输出** : [0，0，' Gfg '，0，0，0，' Best '，0，0，0，0，0，0]

**方法#1:使用`list comprehension + keys()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们通过提取字典的关键字进行查找，来执行为列表检查索引赋值的任务。

```
# Python3 code to demonstrate working of 
# Convert Index Dictionary to List
# Using list comprehension + keys()

# initializing dictionary
test_dict = { 2 : 'Gfg', 4 : 'is', 6 : 'Best' } 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Index Dictionary to List
# Using list comprehension + keys()
res = [test_dict[key] if key in test_dict.keys() else 0 for key in range(10)]

# printing result 
print("The converted list : " + str(res)) 
```

**Output :**

```
The original dictionary is : {2: 'Gfg', 4: 'is', 6: 'Best'}
The converted list : [0, 0, 'Gfg', 0, 'is', 0, 'Best', 0, 0, 0]

```

**方法 2:使用列表理解+ `get()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 get()来提取元素，以便利用 get()的默认值初始化属性来分配默认值。

```
# Python3 code to demonstrate working of 
# Convert Index Dictionary to List
# Using list comprehension + get()

# initializing dictionary
test_dict = { 2 : 'Gfg', 4 : 'is', 6 : 'Best' } 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Index Dictionary to List
# Using list comprehension + get()
res = [test_dict.get(ele, 0) for ele in range(10)]

# printing result 
print("The converted list : " + str(res)) 
```

**Output :**

```
The original dictionary is : {2: 'Gfg', 4: 'is', 6: 'Best'}
The converted list : [0, 0, 'Gfg', 0, 'is', 0, 'Best', 0, 0, 0]

```