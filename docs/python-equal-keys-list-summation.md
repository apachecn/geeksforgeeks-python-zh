# Python |等键列表求和

> 原文:[https://www . geesforgeks . org/python-equal-key-list-summary/](https://www.geeksforgeeks.org/python-equal-keys-list-summation/)

有时候，在使用字典时，我们会遇到一个问题，我们有很多字典，我们需要像键一样求和。这个问题看起来很常见，但复杂的是如果键值是 list，我们需要向相似键的列表中添加元素。让我们讨论一下解决这个问题的方法。

**方法:使用列表理解+ `items() + sum()`**
这个问题可以通过使用列表理解和 sum()来解决，sum()可以用来对列表内容进行求和，items 方法也可以用来获取字典键和值。

```py
# Python3 code to demonstrate working of
# Equal Keys List Summation
# Using items() + list comprehension + sum()

# initializing dictionaries
test_dict1 = {'Gfg' : [1, 2, 3], 'for' : [2, 4], 'CS' : [7, 8]}
test_dict2 = {'Gfg' : [10, 11], 'for' : [5], 'CS' : [0, 18]}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Using items() + list comprehension + sum()
# Equal Keys List Summation
res = {key: sum(value) + sum(test_dict2[key]) for key, value in test_dict1.items()}

# printing result 
print("The summation of dictionary values is : " + str(res))
```

**Output :**

```py
The original dictionary 1 is : {'CS': [7, 8], 'for': [2, 4], 'Gfg': [1, 2, 3]}
The original dictionary 2 is : {'CS': [0, 18], 'for': [5], 'Gfg': [10, 11]}
The summation of dictionary values is : {'CS': 33, 'for': 11, 'Gfg': 27}

```