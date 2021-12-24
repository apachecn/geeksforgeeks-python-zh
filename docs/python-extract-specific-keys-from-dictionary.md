# Python |从字典中提取特定键

> 原文:[https://www . geesforgeks . org/python-从字典中提取特定密钥/](https://www.geeksforgeeks.org/python-extract-specific-keys-from-dictionary/)

在 Python 中，我们有很多字典容器的变体和应用，有时，我们希望对字典中的关键字进行过滤，即只提取特定容器中存在的关键字。让我们讨论一下实现这一点的某些方法。

**方法一:利用字典理解+ `items()`**

这个问题可以通过使用通过希望被过滤的项目功能提取的关键字和字典功能制作所需字典的重建来执行。

```
# Python3 code to demonstrate
# Extracting specifix keys from dictionary
# Using dictionary comprehension + items()

# initializing dictionary
test_dict = {'nikhil' : 1, "akash" : 2, 'akshat' : 3, 'manjeet' : 4}

# printing original list
print("The original dictionary : " + str(test_dict))

# Using dictionary comprehension + items()
# Extracting specifix keys from dictionary
res = {key: test_dict[key] for key in test_dict.keys()
                               & {'akshat', 'nikhil'}}

# print result
print("The filtered dictionary is : " + str(res))
```

**Output :**

```
The original dictionary : {'manjeet': 4, 'akshat': 3, 'akash': 2, 'nikhil': 1}
The filtered dictionary is : {'akshat': 3, 'nikhil': 1}

```

**方法 2:使用`dict()`**

dict 函数可以通过将使用列表理解执行的逻辑转换为字典来执行此任务。

```
# Python3 code to demonstrate
# Extracting specifix keys from dictionary
# Using dict()

# initializing dictionary
test_dict = {'nikhil' : 1, "akash" : 2, 'akshat' : 3, 'manjeet' : 4}

# printing original list
print("The original dictionary : " + str(test_dict))

# Using dict()
# Extracting specifix keys from dictionary
res = dict((k, test_dict[k]) for k in ['nikhil', 'akshat']
                                        if k in test_dict)

# print result
print("The filtered dictionary is : " + str(res))
```

**Output :**

```
The original dictionary : {'manjeet': 4, 'akshat': 3, 'akash': 2, 'nikhil': 1}
The filtered dictionary is : {'akshat': 3, 'nikhil': 1}

```