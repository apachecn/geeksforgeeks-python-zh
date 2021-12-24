# Python |检查一个字典是否是其他字典的子集

> 原文:[https://www . geesforgeks . org/python-check-if-one-dictionary-is-subset-other/](https://www.geeksforgeeks.org/python-check-if-one-dictionary-is-subset-of-other/)

有时候，在使用 Python 时，我们可能会遇到一个问题，如果某个特定的字典是其他字典的一部分，即它是其他字典的子集，那么我们需要找到这个问题。一个在 web 开发领域有巨大潜力的问题，有解决的知识可能是有用的。让我们讨论执行这项任务的某些方法。

**方法#1:使用`all() + items()`**
这个任务可以使用上述两个功能的组合来执行，其中我们使用`all()`检查子字典的所有项目，并使用`items()`获取它的每一对。

```
# Python3 code to demonstrate working of
# Check if one dictionary is subset of other
# Using all() + items()

# Initialize dictionaries
test_dict1 = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'CS' : 5}
test_dict2 = {'gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionaries
print("The original dictionary 1 : " +  str(test_dict1))
print("The original dictionary 2 : " +  str(test_dict2))

# Using all() + items()
# Check if one dictionary is subset of other
res = all(test_dict1.get(key, None) == val for key, val
                                 in test_dict2.items())

# printing result 
print("Does dict2 lie in dict1 ? : " + str(res))
```

**Output :**

> 原词典 1 : {'CS': 5，' is': 2，' best': 3，' gfg': 1，' for': 4}
> 原词典 2 : {'is': 2，' best': 3，' gfg ':1 }
> dict 2 在 dict1 中吗？:真