# Python–将频率字典转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-frequency-dictionary-to-list/](https://www.geeksforgeeks.org/python-convert-frequency-dictionary-to-list/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们需要从字典的值中构造列表。该任务与查找频率相反，可应用于日常编程和 web 开发领域。让我们讨论执行这项任务的某些方法。

> **输入:**【test _ dict = {‘gfg’:3，' ide:】
> **输出:【G4】[‘gfg’、【gfg’、【gfg’、【ide’]**
> 
>  **输入:** test_dict = {“练习”:1，“写”:2，“ide”:4 }
> **输出:** [“练习”，“写”，“写”，“ide”，“ide”，“ide”，“ide”

**方法#1:使用循环**
这是解决这个问题的蛮方法。在这种情况下，我们迭代字典，提取频率，并以该频率复制元素。

```
# Python3 code to demonstrate working of 
# Convert Frequency dictionary to list
# Using loop

# initializing dictionary
test_dict = {'gfg' : 4, 'is' : 2, 'best' : 5}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Convert Frequency dictionary to list
# Using loop
res = []
for key in test_dict:
    for idx in range(test_dict[key]):
        res.append(key)

# printing result 
print("The resultant list : " + str(res)) 
```

**Output :**

> 原词典:{'is': 2，' best': 5，' gfg': 4}
> 结果列表:['is '，' is '，' best '，' best '，' best '，' best '，' best '，' gfg '，' gfg '，' gfg']

**方法 2:使用列表理解**
该方法在工作方面与上述方法类似。这是上述方法的简称。

```
# Python3 code to demonstrate working of 
# Convert Frequency dictionary to list
# Using list comprehension

# initializing dictionary
test_dict = {'gfg' : 4, 'is' : 2, 'best' : 5}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Convert Frequency dictionary to list
# Using list comprehension
res = [[key] * test_dict[key] for key in test_dict]

# printing result 
print("The resultant list : " + str(res)) 
```

**Output :**

> 原词典:{'is': 2，' best': 5，' gfg': 4}
> 结果列表:['is '，' is '，' best '，' best '，' best '，' best '，' best '，' gfg '，' gfg '，' gfg']