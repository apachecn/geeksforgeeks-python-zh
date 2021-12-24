# Python |提取变量中字典的键值

> 原文:[https://www . geesforgeks . org/python-提取-变量字典键值/](https://www.geeksforgeeks.org/python-extract-key-value-of-dictionary-in-variables/)

有时，在使用字典时，我们可能会面临这样一个问题，即我们可能只有一个单例字典，即只有一个键值对的字典，并且需要在单独的变量中获取该对。这种问题会出现在日常编程中。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`items()`**
这个问题可以使用`items`函数来解决，该函数执行提取键值对的任务，并使用第 0 个索引给我们第一个键值对。仅适用于 Python2。

```py
# Python code to demonstrate working of
# Extracting key-value of dictionary in variables
# Using items()

# Initialize dictionary
test_dict = {'gfg' : 1}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using items()
# Extracting key-value of dictionary in variables
key, val = test_dict.items()[0]

# printing result 
print("The 1st key of dictionary is : " + str(key))
print("The 1st value of dictionary is : " + str(val))
```

**Output :**

```py
The original dictionary : {'gfg': 1}
The 1st key of dictionary is : gfg
The 1st value of dictionary is : 1

```