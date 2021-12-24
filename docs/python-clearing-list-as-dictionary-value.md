# Python |清除列表作为字典值

> 原文:[https://www . geesforgeks . org/python-clearing-list-as-dictionary-value/](https://www.geeksforgeeks.org/python-clearing-list-as-dictionary-value/)

清除列表是一个常见的问题，对它的解决方案已经讨论了很多次。但有时，我们没有本地列表，但列表是字典键的一个值。清除它不像清除原始列表那么容易。让我们讨论一下实现这一点的某些方法。

**方法#1:使用 loop + `clear()`**
这是我们可以执行这个特定功能的最通用的方法。我们只是运行一个循环，直到最后一个字典键，并使用 clear 函数清除键的列表值。

```py
# Python3 code to demonstrate
# clearing list as dict. value
# using loop + clear()

# initializing dict.
test_dict = {"Akash" : [1, 4, 3],
             "Nikhil" : [3, 4, 1],
             "Akshat" : [7, 8]}

# printing original dict
print("The original dict : " + str(test_dict))

# using loop + clear()
# clearing list as dict. value
for key in test_dict:
    test_dict[key].clear()

# print result
print("The dictionary after clearing value list : " + str(test_dict))
```

**Output :**

> 原字典:{'Nikhil': [3，4，1]，' Akshat': [7，8]，' Akash': [1，4，3]}
> 清除值列表后的字典:{'Nikhil': []，' Akshat': []，' Akash': []}