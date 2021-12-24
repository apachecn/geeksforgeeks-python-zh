# Python |基于选择列表

中的值过滤字典键

> 原文:[https://www . geesforgeks . org/python-filter-dictionary-key-based-on-values-in-selective-list/](https://www.geeksforgeeks.org/python-filter-dictionary-key-based-on-the-values-in-selective-list/)

在 Python 中，有时我们只需要获取一些字典键，而不是全部。这个问题在 web 开发中很常见，我们只需要从某个给定的列表中获取选择性的字典键。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解**
列表理解可以用来解决这个特殊的问题。这只是执行它的速记方式，而不是编写循环。

```py
# Python3 code to demonstrate 
# getting selective dictionary keys
# using list comprehension

# initializing dictionary
test_dict = {"Akash" : 1, "Akshat" : 2, "Nikhil" : 3, "Manjeet" : 4}

# initializing selective list keys 
select_list = ['Manjeet', 'Nikhil']

# printing original dictionary
print ("The original dictionary is : " + str(test_dict))

# printing selective list 
print ("The selective list is : " + str(select_list))

# using list comprehension
# getting selective dictionary keys 
res = [test_dict[i] for i in select_list if i in test_dict]

# printing result 
print ("The selected values from list keys is : " +  str(res))
```

**Output:**

> 原始字典为:{'Nikhil': 3，' Akshat': 2，' Manjeet': 4，' Akash': 1}
> 选择列表为:['Manjeet '，' Nikhil']
> 从列表键中选择的值为:[4，3]