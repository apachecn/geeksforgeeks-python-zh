# Python |在字典中查找最近的 Key

> 原文:[https://www . geesforgeks . org/python-在字典中查找最近的键/](https://www.geeksforgeeks.org/python-find-the-closest-key-in-dictionary/)

python 中字典中关键字的搜索已经讨论过多次。但有时，我们可能会遇到这样的问题，即我们需要获取与给定密钥最接近的密钥。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `keys()` + lambda**
上述功能的组合可用于执行在字典中查找最近的键的特定任务。key 函数可以用来访问字典中的键，lambda 函数可以用来制定逻辑和列表理解，以便将所有这些应用到整个列表中。

```py
# Python3 code to demonstrate working of
# Closest key in dictionary
# Using list comprehension + keys() + lambda

# initializing dictionary
test_dict = {13 : 'Hi', 15 : 'Hello',  16 : 'Gfg'}

# initializing nearest key
search_key = 15.6

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using list comprehension + keys() + lambda
# Closest key in dictionary
res = test_dict.get(search_key) or test_dict[
      min(test_dict.keys(), key = lambda key: abs(key-search_key))]

# printing result 
print("The value to the closest key : " + str(res))
```

**Output :**

```py
The original dictionary is : {16: 'Gfg', 13: 'Hi', 15: 'Hello'}
The value to the closest key : Gfg

```