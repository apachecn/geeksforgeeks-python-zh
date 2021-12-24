# Python |获取字典中的前 K 项

> 原文:[https://www . geesforgeks . org/python-get-first-k-items-in-dictionary/](https://www.geeksforgeeks.org/python-get-first-k-items-in-dictionary/)

在使用字典时，我们可能会遇到这样一个问题:我们可能只需要在字典中获取一些初始关键字。这个问题通常发生在 web 开发领域。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`items()` +列表切片**
要解决这个问题，必须隐含以上功能的组合。`items`功能可以获取所有字典项，主任务通过列表切片完成，限制了字典键值对。

```
# Python3 code to demonstrate working of
# Get first K items in dictionary
# Using items() + list slicing

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'CS' : 5}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Initialize limit
K = 3

# Using items() + list slicing
# Get first K items in dictionary
res = dict(list(test_dict.items())[0: K])

# printing result 
print("Dictionary limited by K is : " + str(res))
```

**Output :**

> 原词典:{'is': 2，' CS': 5，' best': 3，' gfg': 1，' for': 4}
> 受 K 限制的词典是:{'is': 2，' CS': 5，' best': 3}