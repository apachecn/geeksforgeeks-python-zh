# Python–更改字典列表中的键类型

> 原文:[https://www . geeksforgeeks . org/python-变更-字典中的键类型-列表/](https://www.geeksforgeeks.org/python-change-type-of-key-in-dictionary-list/)

有时，在处理数据时，我们会遇到一个问题，即我们需要更改字典列表中特定键的值的类型。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{'gfg': 9，' best': (7，2)，' is': '4'}，{'is': '2'}]
> **输出** : [{'gfg': 9，' best': (7，2)，' is': 4}，{'is': 2}]
> 
> **输入**:test _ list =[{ ' is ':' 98393 ' }]
> **输出** : [{'is' : 98393}]

**方法#1:使用循环**
这是蛮力的方式来处理这个问题。在这种情况下，我们迭代所有列表元素和字典键，并将所需字典键的值转换为所需的类型。

```py
# Python3 code to demonstrate working of 
# Change type of key in Dictionary list
# Using loop

# initializing list
test_list = [{'gfg' : 1, 'is' : '56', 'best' : (1, 2)}, 
            {'gfg' : 5, 'is' : '12', 'best' : (6, 2)},
            {'gfg' : 3, 'is' : '789', 'best' : (7, 2)}]

# printing original list
print("The original list is : " + str(test_list))

# initializing change key 
chnge_key = 'is'

# Change type of key in Dictionary list
# Using loop
for sub in test_list:
        sub[chnge_key] = int(sub[chnge_key])

# printing result 
print("The converted Dictionary list : " + str(test_list)) 
```

**Output :**

> 原始列表为:[{'is': '56 '，' gfg': 1，' best': (1，2)}，{'is': '12 '，' gfg': 5，' best': (6，2)}，{'is': '789 '，' gfg': 3，' best': (7，2)}]
> 转换后的 Dictionary 列表:[{'is': 56，' gfg': 1，' best': (1，2)}，{'is': 12，' gfg': 5，' best': (6，2)}，{ '

**方法 2:使用列表理解**
这个任务也可以使用列表理解作为速记来执行。在这种情况下，我们使用与上面相同的方法以更短的方式迭代列表。

```py
# Python3 code to demonstrate working of 
# Change type of key in Dictionary list
# Using list comprehension

# initializing list
test_list = [{'gfg' : 1, 'is' : '56', 'best' : (1, 2)}, 
            {'gfg' : 5, 'is' : '12', 'best' : (6, 2)},
            {'gfg' : 3, 'is' : '789', 'best' : (7, 2)}]

# printing original list
print("The original list is : " + str(test_list))

# initializing change key 
chnge_key = 'is'

# Change type of key in Dictionary list
# Using list comprehension
res = [{key : (int(val) if key == chnge_key else val)
                        for key, val in sub.items()}
                        for sub in test_list]

# printing result 
print("The converted Dictionary list : " + str(res)) 
```

**Output :**

> 原始列表为:[{'is': '56 '，' gfg': 1，' best': (1，2)}，{'is': '12 '，' gfg': 5，' best': (6，2)}，{'is': '789 '，' gfg': 3，' best': (7，2)}]
> 转换后的 Dictionary 列表:[{'is': 56，' gfg': 1，' best': (1，2)}，{'is': 12，' gfg': 5，' best': (6，2)}，{ '