# Python–连接字典字符串值

> 原文:[https://www . geesforgeks . org/python-concatenate-dictionary-string-values/](https://www.geeksforgeeks.org/python-concatenate-dictionary-string-values/)

有时，在使用字典时，我们可能会遇到效用问题，需要在字典的公共键之间执行基本操作。这可以扩展到要执行的任何操作。让我们在本文中讨论相似键值的字符串连接以及解决方法。

**方法#1:使用字典理解+ `keys()`**
以上两者的结合可以用来执行这个特定的任务。这只是较长循环方法的简写，可以用来在一行中执行此任务。

```
# Python3 code to demonstrate working of
# Concatenate Dictionary string values
# Using dictionary comprehension + keys()

# Initialize dictionaries
test_dict1 = {'gfg' : 'a', 'is' : 'b', 'best' : 'c'}
test_dict2 = {'gfg' : 'd', 'is' : 'e', 'best' : 'f'}

# printing original dictionaries 
print("The original dictionary 1 : " + str(test_dict1))
print("The original dictionary 2 : " + str(test_dict2))

# Using dictionary comprehension + keys()
# Concatenate Dictionary string values
res = {key: test_dict1[key] + test_dict2.get(key, '') for key in test_dict1.keys()}

# printing result 
print("The string concatenation of dictionary is : " + str(res))
```

**Output :**

```
The original dictionary 1 : {'gfg': 'a', 'is': 'b', 'best': 'c'}
The original dictionary 2 : {'gfg': 'd', 'is': 'e', 'best': 'f'}
The string concatenation of dictionary is : {'gfg': 'ad', 'is': 'be', 'best': 'cf'}

```