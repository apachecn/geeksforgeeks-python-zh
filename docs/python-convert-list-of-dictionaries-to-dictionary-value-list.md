# Python–将字典列表转换为字典值列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-dictionary-to-dictionary-value-list/](https://www.geeksforgeeks.org/python-convert-list-of-dictionaries-to-dictionary-value-list/)

给定一个字典列表，转换为具有与 as 值列表中的所有值映射的相同键的字典。

> **输入**:test _ list =[{“Gfg”:6，“is”:9，“best”:10 }，
> {“Gfg”:8，“is”:11，“best”:19 }]
> **输出**:{‘Gfg’:[6，8]，‘is’:[9，11]，‘best’:[10，19]}
> **解释**:将“Gfg”的 6，8 映射为值列表，每隔一个类似。
> 
> **输入**:test _ list =[{“Gfg”:6、【最佳】:10}、
> {“Gfg”:8、【最佳】:19}]
> **输出**:{“Gfg”:【6、8】、【最佳】:10、19】}
> **解释**:同上，转换。

**方法#1:使用循环**

这是解决这个问题的粗暴方法。在这种情况下，我们遍历所有的字典，提取每个键，并在嵌套循环中转换为所需的字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert list of dictionaries to Dictionary Value list
# Using loop
from collections import defaultdict

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# using loop to get dictionaries
# defaultdict used to make default empty list 
# for each key
res = defaultdict(list)
for sub in test_list:
    for key in sub:
        res[key].append(sub[key])

# printing result 
print("The extracted dictionary : " + str(dict(res)))
```

**Output**

```py
The original list : [{'Gfg': 6, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 2, 'is': 16, 'best': 10}, {'Gfg': 12, 'is': 1, 'best': 8}, {'Gfg': 22, 'is': 6, 'best': 8}]
The extracted dictionary : {'Gfg': [6, 8, 2, 12, 22], 'is': [9, 11, 16, 1, 6], 'best': [10, 19, 10, 8, 8]}

```

**方法二:使用列表理解+词典理解**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用字典理解来构造字典，使用列表理解来从原始列表中提取值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert list of dictionaries to Dictionary Value list
# Using list comprehension + dictionary comprehension
from collections import defaultdict

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# dictionary and list comprehension 
# for shorthand to solution of problem
res = defaultdict(list)
{res[key].append(sub[key]) for sub in test_list for key in sub} 

# printing result 
print("The extracted dictionary : " + str(dict(res)))
```

**Output**

```py
The original list : [{'Gfg': 6, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 2, 'is': 16, 'best': 10}, {'Gfg': 12, 'is': 1, 'best': 8}, {'Gfg': 22, 'is': 6, 'best': 8}]
The extracted dictionary : {'Gfg': [6, 8, 2, 12, 22], 'is': [9, 11, 16, 1, 6], 'best': [10, 19, 10, 8, 8]}

```