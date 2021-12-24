# Python–使用列表元素提取字典项目

> 原文:[https://www . geesforgeks . org/python-extract-dictionary-items-with-list-elements/](https://www.geeksforgeeks.org/python-extract-dictionary-items-with-list-elements/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要从字典中提取构成列表中所有元素的所有项目。这种问题可能发生在竞争编程和 web 开发等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'gfg' : [4，6，10]，' is' : [12]}
> **输出** : {'gfg': [4，6，10]}
> 
> **输入** : test_dict = {'gfg' : [4，6，10]}
> **输出** : {'gfg': [4，6，10]}

**方法#1:使用`set() + dictionary comprehension + items()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们首先减少列表元素以消除重复，使用 items()提取字典项，并使用字典理解来构建所需的字典。

```
# Python3 code to demonstrate working of 
# Extract dictionary items with List elements
# Using set() + dictionary comprehension + items()

# helpr_fnc
def hlper_fnc(req_list, test_dict):
    temp = set(req_list)
    temp2 = { key: set(val) for key, val in test_dict.items() }
    return { key: val for key, val in test_dict.items() if temp2[key].issubset(temp)}

# initializing dictionary
test_dict = {'gfg' : [4, 6], 'is' : [10], 'best' : [4, 5, 7]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing req_list 
req_list = [4, 6, 10]

# Extract dictionary items with List elements
# Using set() + dictionary comprehension + items()
res = hlper_fnc(req_list, test_dict)

# printing result 
print("The extracted dictionary: " + str(res)) 
```

**Output :**

> 原始字典:{'is': [10]，' best': [4，5，7]，' gfg': [4，6]}
> 提取的字典:{'is': [10]，' gfg': [4，6]}

**方法二:使用`all()` +字典理解**
以上功能的组合可以用来解决这个问题。这是一个单行解决方案，使用 all()检查元素成员资格以决定过滤。词典理解担负着构建词典的任务。

```
# Python3 code to demonstrate working of 
# Extract dictionary items with List elements
# Using all() + dictionary comprehension

# initializing dictionary
test_dict = {'gfg' : [4, 6], 'is' : [10], 'best' : [4, 5, 7]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing req_list 
req_list = [4, 6, 10]

# Extract dictionary items with List elements
# Using all() + dictionary comprehension
res = {key: val for key, val in test_dict.items() if all(vals in req_list for vals in val)}

# printing result 
print("The extracted dictionary: " + str(res)) 
```

**Output :**

```
The original dictionary : {'is': [10], 'best': [4, 5, 7], 'gfg': [4, 6]}
The extracted dictionary: {'is': [10], 'gfg': [4, 6]}

```