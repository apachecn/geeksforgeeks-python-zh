# Python–字典中的键值列表对

> 原文:[https://www . geesforgeks . org/python-key-value-list-pairing-in-dictionary/](https://www.geeksforgeeks.org/python-key-value-list-pairings-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即我们需要将所有键与所有值配对，以形成一个包含所有可能配对的字典。这可以应用于许多领域，包括日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这个任务可以使用这个方法来执行。在这种情况下，我们手动提取每个键，然后用它们的所有值进行迭代，以形成新的字典列表。这具有仅适用于某些键的缺点。

```
# Python3 code to demonstrate working of 
# Key Value list pairings in Dictionary
# Using list comprehension

# initializing dictionary
test_dict = {'gfg' : [7, 8],
             'best' : [10, 11, 7]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Key Value list pairings in Dictionary
# Using list comprehension
res = [{'gfg': i, 'best': j} for i in test_dict['gfg']
                           for j in test_dict['best']]

# printing result 
print("All key value paired List : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': [7，8]，' best': [10，11，7]}
> 所有键值配对列表:[{'gfg': 7，' best': 10}，{'gfg': 7，' best': 11}，{ ' gfg ':7 ' }，{'gfg': 8，' best': 10}，{'gfg': 8，' best': 11}，{'gfg': 8，' best': 7}]