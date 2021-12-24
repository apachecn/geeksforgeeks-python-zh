# Python–常用项目字典值列表

> 原文:[https://www . geesforgeks . org/python-common-items-dictionary-value-list/](https://www.geeksforgeeks.org/python-common-items-dictionary-value-list/)

联合的功能已经被讨论过很多次了。但是有时候，我们可以有一个更复杂的容器，在其中我们需要检查以字典关键字形式出现的列表的交集。让我们讨论解决这类问题的某些方法。

**方法#1:使用循环**
使用循环是执行这一特定任务的一种天真的蛮力方法。在这个方法中，我们检查两个列表中的键。我们甚至检查在其他中完全不存在的键来添加它的整个列表值。

```py
# Python3 code to demonstrate
# Common elements Dictionary Value List
# using loops

# initializing dicts
test_dict1 = { "Key1" : [1, 3, 4], "key2" : [4, 5] }
test_dict2 = { "Key1" : [1, 7, 3] }

# printing original dicts
print("The original dict 1 : " + str(test_dict1))
print("The original dict 2 : " + str(test_dict2))

# using loops
# Common elements Dictionary Value List
res = dict()
for key in test_dict1: 
    if key in test_dict2: 
        res[key] = []
        for val in test_dict1[key]:
            if val in test_dict2[key]:
                res[key].append(val)

# print result
print("The dicts after intersection is : " + str(res))
```

**Output :**

```py
The original dict 1 : {'Key1': [1, 3, 4], 'key2': [4, 5]}
The original dict 2 : {'Key1': [1, 7, 3]}
The dicts after intersection is : {'Key1': [1, 3]}

```