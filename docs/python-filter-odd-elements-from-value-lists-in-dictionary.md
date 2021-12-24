# Python–从字典中的值列表中过滤奇数元素

> 原文:[https://www . geeksforgeeks . org/python-filter-odd-elements-from-value-list-in-dictionary/](https://www.geeksforgeeks.org/python-filter-odd-elements-from-value-lists-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即需要从字典的值列表中移除奇数元素。这可以应用于许多领域，包括网络开发。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+词典理解**
这是可以执行这个任务的蛮力一衬。在本文中，我们使用字典理解来重新构建新字典，其中使用列表理解来执行值列表中的数据过滤和迭代。

```
# Python3 code to demonstrate working of 
# Remove odd elements from value lists in dictionary
# Using list comprehension + dictionary comprehension

# initializing Dictionary
test_dict = {'gfg' : [1, 3, 4, 10], 'is' : [1, 2, 8], 'best' : [4, 3, 7]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Remove odd elements from value lists in dictionary
# Using list comprehension + dictionary comprehension
res = {key: [idx for idx in val if idx % 2] 
          for key, val in test_dict.items()}

# printing result 
print("The filtered values are : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': [1，3，4，10]，' best': [4，3，7]，' is': [1，2，8]}
> 筛选值为:{'gfg': [1，3]，' is': [1]，' best': [3，7]}