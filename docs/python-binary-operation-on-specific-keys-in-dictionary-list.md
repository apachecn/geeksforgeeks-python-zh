# Python–字典列表中特定键的二进制运算

> 原文:[https://www . geesforgeks . org/python-binary-operation-on-specific-key-in-dictionary-list/](https://www.geeksforgeeks.org/python-binary-operation-on-specific-keys-in-dictionary-list/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们需要在整个列表中对字典中的某些键执行某些操作并返回结果。这种问题在涉及数据的领域很常见，比如 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'best': 8，' Gfg': 13}，{'is': 5，' for': 9，' best': 15，' Gfg': 7，'极客':7}]
> **输出** : [(0，104)，(1，105)]
> 
> **输入** : test_list = [{'Gfg' : 3，' best' : 10}]
> **输出** : [(0，30)]

**方法#1 : loop + `enumerate()`**
以上功能的组合可以用来解决这个问题。这是一种蛮力方法，我们循环遍历每个字典列表，执行操作并存储结果。

```py
# Python3 code to demonstrate working of 
# Binary operation on specific keys in Dictionary List
# Using loop + enumerate()

# initializing list
test_list = [{'Gfg' : 5, 'is' : 6, 'best' : 7, 'for' : 8, 'geeks' : 10},
             {'Gfg' : 9, 'is' : 4, 'best' : 10, 'for' : 4, 'geeks' :7},
             {'Gfg' : 2, 'is' : 10, 'best' : 8, 'for' : 9, 'geeks' : 3}]

# printing original list
print("The original list is : " + str(test_list))

# initializing keys 
op1_key = 'Gfg'
op2_key = 'best'

# Binary operation on specific keys in Dictionary List
# Using loop + enumerate()
res = []
for idx, val in enumerate(test_list):
    res.append((idx, val[op1_key] * val[op2_key]))

# printing result 
print("The constructed result list : " + str(res)) 
```

**Output :**

> 原始列表为:[{“极客”:10，“for”:8，“Gfg”:5，“is”:6，“best”:7 }，{“极客”:7，“for”:4，“Gfg”:9，“is”:4，“best”:10 }，{“极客”:3，“for”:9，“Gfg”:2，“is”:10，“best”:8 }]
> 
> 构造的结果列表:[(0，35)，(1，90)，(2，16)]

**方法 2:使用列表理解+ `enumerate()`**
以上功能的组合也可以用来解决这个问题。在这种情况下，我们以速记的方式使用列表理解来执行类似的任务。

```py
# Python3 code to demonstrate working of 
# Binary operation on specific keys in Dictionary List
# Using list comprehension + enumerate()

# initializing list
test_list = [{'Gfg' : 5, 'is' : 6, 'best' : 7, 'for' : 8, 'geeks' : 10},
             {'Gfg' : 9, 'is' : 4, 'best' : 10, 'for' : 4, 'geeks' :7},
             {'Gfg' : 2, 'is' : 10, 'best' : 8, 'for' : 9, 'geeks' : 3}]

# printing original list
print("The original list is : " + str(test_list))

# initializing keys 
op1_key = 'Gfg'
op2_key = 'best'

# Binary operation on specific keys in Dictionary List
# Using list comprehension + enumerate()
res = [(idx, val[op1_key] * val[op2_key]) for idx, val in enumerate(test_list)]

# printing result 
print("The constructed result list : " + str(res)) 
```

**Output :**

> 原始列表为:[{“极客”:10，“for”:8，“Gfg”:5，“is”:6，“best”:7 }，{“极客”:7，“for”:4，“Gfg”:9，“is”:4，“best”:10 }，{“极客”:3，“for”:9，“Gfg”:2，“is”:10，“best”:8 }]
> 
> 构造的结果列表:[(0，35)，(1，90)，(2，16)]