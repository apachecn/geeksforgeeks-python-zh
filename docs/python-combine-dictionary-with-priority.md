# Python–优先组合字典

> 原文:[https://www . geeksforgeeks . org/python-combine-dictionary-with-priority/](https://www.geeksforgeeks.org/python-combine-dictionary-with-priority/)

有时，在处理字典数据时，我们可能会遇到需要合并两个字典的问题。这是很常见的问题。但是这种方法的一种变体是组合字典，如果两个键在字典中冲突，则优先使用特定的字典。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict1 = {'Gfg' : 6，' is' : 15，' best' : 13 }
> test _ dict 2 = { ' Gfg ':8，' is' : 10}
> **输出** : {'Gfg': 8，' best ':13，' is' : 10}
> 
> **输入**:test _ dict 1 = { ' Gfg ':6 }
> test _ dict 2 = { ' Gfg ':8 }
> **输出** : {'Gfg': 8}

**方法#1:使用`copy()` +循环**
以上功能的组合可以用来解决这个问题。这是解决这个问题的粗暴方法。在本例中，我们执行 copy()来深度复制字典值，然后使用优先级字典覆盖这些值。

```py
# Python3 code to demonstrate working of 
# Combine dictionary with priority
# Using loop + copy()

# initializing dictionaries
test_dict1 = {'Gfg' : 1, 'is' : 2, 'best' : 3}
test_dict2 = {'Gfg' : 4, 'is' : 10, 'for' : 7, 'geeks' : 12}

# printing original dictionaries
print("The original dictionary is 1 : " + str(test_dict1))
print("The original dictionary is 2 : " + str(test_dict2))

# declaring priority order
prio_dict = {1 : test_dict2, 2: test_dict1}

# Combine dictionary with priority
# Using loop + copy()
res = prio_dict[2].copy()
for key, val in prio_dict[1].items():
    res[key] = val

# printing result 
print("The dictionary after combination : " + str(res)) 
```

**Output :**

> 原词典为 1 : {'is': 2，' best': 3，' Gfg': 1}
> 原词典为 2 : {'for': 7，' is': 10，'极客':12，' Gfg': 4}
> 组合后的词典:{'for': 7，' is': 10，' best': 3，'极客':12，' Gfg': 4}

**方法 2:使用`** operator`**
这是解决这个问题的新方法，我们可以绑定两个字典，绑定在第二位的字典优先于初始字典的键。

```py
# Python3 code to demonstrate working of 
# Combine dictionary with priority
# Using ** operator

# initializing dictionaries
test_dict1 = {'Gfg' : 1, 'is' : 2, 'best' : 3}
test_dict2 = {'Gfg' : 4, 'is' : 10, 'for' : 7, 'geeks' : 12}

# printing original dictionaries
print("The original dictionary is 1 : " + str(test_dict1))
print("The original dictionary is 2 : " + str(test_dict2))

# declaring priority order
prio_dict = {1 : test_dict2, 2: test_dict1}

# Combine dictionary with priority
# Using ** operator
res = {**prio_dict[2], **prio_dict[1]} 

# printing result 
print("The dictionary after combination : " + str(res)) 
```

**Output :**

> 原词典为 1 : {'is': 2，' best': 3，' Gfg': 1}
> 原词典为 2 : {'for': 7，' is': 10，'极客':12，' Gfg': 4}
> 组合后的词典:{'for': 7，' is': 10，' best': 3，'极客':12，' Gfg': 4}