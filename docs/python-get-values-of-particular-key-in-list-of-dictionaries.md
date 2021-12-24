# Python |获取字典列表中特定键的值

> 原文:[https://www . geesforgeks . org/python-获取字典列表中特定键的值/](https://www.geeksforgeeks.org/python-get-values-of-particular-key-in-list-of-dictionaries/)

有时，我们可能需要一种方法，从字典列表中获取特定关键字的所有值。这种问题在 web 开发领域有很多应用，在这些领域中，我们有时有一个 json，只需要从记录中获取单个列。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
使用列表理解是相当直接的方法来执行这个特定的任务。在这种情况下，我们只需在字典列表中迭代所需的值。

```py
# Python3 code to demonstrate working of
# Get values of particular key in list of dictionaries
# Using list comprehension

# initializing list
test_list = [{'gfg' : 1, 'is' : 2, 'good' : 3}, 
             {'gfg' : 2}, {'best' : 3, 'gfg' : 4}]

# printing original list
print("The original list is : " + str(test_list))

# Using list comprehension
# Get values of particular key in list of dictionaries
res = [ sub['gfg'] for sub in test_list ]

# printing result 
print("The values corresponding to key : " + str(res))
```

**Output :**

> 原始列表为:[{'is': 2，' gfg': 1，' good': 3}，{'gfg': 2}，{'best': 3，' gfg': 4}]
> 键对应的值:[1，2，4]