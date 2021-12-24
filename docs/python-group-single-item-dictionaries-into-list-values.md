# Python–将单项词典分组到列表值中

> 原文:[https://www . geesforgeks . org/python-group-单项-词典-进入列表-值/](https://www.geeksforgeeks.org/python-group-single-item-dictionaries-into-list-values/)

给定单项词典列表，根据相似值将它们分组到词典值列表中。

> **输入**:[{“Gfg”:3 }、{“is”:8 }、{“Gfg”:18 }、{“Best”:33 }]
> **输出**:{“Gfg”:[3，18]、“is”:[8]、“Best”:[33]}
> **解释**:各键转换为列表值和字典。
> 
> **输入**:[{“Gfg”:3 }、{“Gfg”:8 }、{“Gfg”:18 }、{“最佳”:33}]
> **输出**:{“Gfg”:[3，18，8]、“‘最佳’:[33]}
> **解释**:各键转换为列表值和字典。

**方法#1:使用 setdefault() +循环**

这是执行这项任务的粗暴方式。在本例中，我们使用循环遍历所有字典值，并使用 setdefault()为公共键分配其对应的分组值列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Group single item dictionaries into List values
# Using setdefault() + loop

# initializing lists
test_list = [{"Gfg" : 3}, {"is": 8}, {"Best": 10}, {"Gfg": 18}, {"Best": 33}]

# printing original list
print("The original list : " + str(test_list))

res = {}

# using loop to loop through each dictionary
for idx in test_list:

    # items() to extract item
    for key, val in idx.items():

        # setdefault performs task of setting empty list value as default
        res.setdefault(key, []).append(val)

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```
The original list : [{'Gfg': 3}, {'is': 8}, {'Best': 10}, {'Gfg': 18}, {'Best': 33}]
The constructed dictionary : {'Gfg': [3, 18], 'is': [8], 'Best': [10, 33]}

```

**方法 2:使用 defaultdict() + *运算符+循环**

这是执行这项任务的另一种方式。在本文中，我们使用 defaultdict()进行空列表初始化。运算符*用于解包字典项，循环用于循环遍历字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Group single item dictionaries into List values
# Using defaultdict() + * operator + loop
from collections import defaultdict

# initializing lists
test_list = [{"Gfg" : 3}, {"is": 8}, {"Best": 10}, {"Gfg": 18}, {"Best": 33}]

# printing original list
print("The original list : " + str(test_list))

res = defaultdict(list)
for ele in test_list:

    # using * operator to unpack
    # reducing one loop
    key, val = tuple(*ele.items())
    res[key].append(val)

# printing result 
print("The constructed dictionary : " + str(dict(res)))
```

**Output**

```
The original list : [{'Gfg': 3}, {'is': 8}, {'Best': 10}, {'Gfg': 18}, {'Best': 33}]
The constructed dictionary : {'Gfg': [3, 18], 'is': [8], 'Best': [10, 33]}

```