# Python–在字典中更改键大小写

> 原文:[https://www . geesforgeks . org/python-change-key-case-in-dictionary/](https://www.geeksforgeeks.org/python-change-keys-case-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，需要对键的情况进行操作。这可能在许多领域有应用，包括学校编程和数据领域。让我们讨论解决这个任务的方法。

> **输入** : test_dict = {'Gfg' : {'a' : 5，' B ':{ ' BEST ':6 } }
> **输出** : {'GFG': {'A': 5，' b' : {'best' : 6}}}
> 
> **输入** : test_dict = {'Gfg' : 6}
> **输出** : {'GFG': 6}

**方法:使用`isinstance() + toupper()` +递归+循环**
以上功能的组合也可以用来解决这个问题。在本文中，我们使用 toupper()来执行键的大写，递归也用于在嵌套键中执行键操作。isinstance()用于检查嵌套是否是字典。

```
# Python3 code to demonstrate working of 
# Change Keys Case in Dictionary
# Using isinstance() + toupper() + recursion + loop

# helper function
def keys_upper(test_dict):
    res = dict()
    for key in test_dict.keys():
        if isinstance(test_dict[key], dict):
            res[key.upper()] = keys_upper(test_dict[key])
        else:
            res[key.upper()] = test_dict[key]
    return res

# initializing dictionary
test_dict = {'Gfg' : {'a' : 5, 'b' : 6}, 'is' : {'for' :2}, 'best': 3}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Change Keys Case in Dictionary
# Using isinstance() + toupper() + recursion + loop
res = keys_upper(test_dict)

# printing result 
print("The modified dictionary : " + str(res)) 
```

**Output :**

```
The original dictionary : {'is': {'for': 2}, 'Gfg': {'b': 6, 'a': 5}, 'best': 3}
The modified dictionary : {'GFG': {'A': 5, 'B': 6}, 'IS': {'FOR': 2}, 'BEST': 3}

```