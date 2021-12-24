# Python–从值子串中提取关键字

> 原文:[https://www . geesforgeks . org/python-从值中提取键-子串/](https://www.geeksforgeeks.org/python-extracting-key-from-value-substring/)

有时候，在使用 Python 字典时，我们会遇到一个问题，需要从给定的值中找到键，从键的值中查询子串。这种问题很常见，在包括 web 开发在内的许多领域都有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {1 : 'Gfg 最好'，2 : 'CS 最好' }
> 输出:【1，2】
> 
> **输入** : test_dict = {1 : 'best'}
> 输出 : [1]

**方法#1:使用 loop + `items()`**
以上功能的组合，可以用来解决这个问题。在这种情况下，我们使用 items()提取字典值，并使用 loop 使用“In”运算符检查子字符串。

```
# Python3 code to demonstrate working of 
# Extracting Key from Value Substring
# Using loop + items()

# initializing dictionary
test_dict = {1 : 'Gfg is good', 2 : 'Gfg is best', 3 : 'Gfg is on top'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing search_word 
srch_wrd = 'best'

# Extracting Key from Value Substring
# Using loop + items()
res = []
for key, val in test_dict.items():
    if srch_wrd in val:
        res.append(key)

# printing result 
print("The Corresponding key : " + str(res)) 
```

**Output :**

> 原词典:{1: 'Gfg 好'，2: 'Gfg 最好'，3: 'Gfg 在上面' }
> 对应键:[2]

**方法 2:使用列表理解**
这是另一种可以执行该任务的方式。在这种情况下，我们以紧凑的方式在一个衬垫中执行上述方法。

```
# Python3 code to demonstrate working of 
# Extracting Key from Value Substring
# Using list comprehension

# initializing dictionary
test_dict = {1 : 'Gfg is good', 2 : 'Gfg is best', 3 : 'Gfg is on top'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing search_word 
srch_wrd = 'best'

# Extracting Key from Value Substring
# Using list comprehension
res = [key for key, val in test_dict.items() if srch_wrd in val]

# printing result 
print("The Corresponding key : " + str(res)) 
```

**Output :**

> 原词典:{1: 'Gfg 好'，2: 'Gfg 最好'，3: 'Gfg 在上面' }
> 对应键:[2]