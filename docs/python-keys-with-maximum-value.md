# Python |最大值键

> 原文:[https://www . geesforgeks . org/python-key-with-maximum-value/](https://www.geeksforgeeks.org/python-keys-with-maximum-value/)

很多时候，我们可能会遇到这样的问题，我们不仅需要找到值，还需要找到整个字典中最大值的对应键。让我们讨论执行这项任务的某些方法。

**方法#1:使用`max() + list comprehension + values()`**
上述功能的组合可用于执行该特定任务。在这种情况下，使用 max 函数提取最大值，而使用 values()提取字典的值。列表理解用于迭代字典以匹配具有最大值的关键字。

```
# Python3 code to demonstrate working of
# Keys with Maximum value
# Using max() + list comprehension + values()

# initializing dictionary
test_dict = {'Gfg' : 2, 'for' : 1, 'CS' : 2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using max() + list comprehension + values()
# Keys with Maximum value
temp = max(test_dict.values())
res = [key for key in test_dict if test_dict[key] == temp]

# printing result 
print("Keys with maximum values are : " + str(res))
```

**Output :**

```
The original dictionary is : {'CS': 2, 'Gfg': 2, 'for': 1}
Keys with maximum values are : ['CS', 'Gfg']

```