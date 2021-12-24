# Python–通过前缀分组将列表转换为键值列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-key-value-list-by-prefix-group/](https://www.geeksforgeeks.org/python-convert-list-to-key-value-list-by-prefix-grouping/)

给定一个列表，将其转换为连续的键值列表，按前缀分组。

> **输入**:test _ list =[“GFG-1”，4，6，“GFG-2”，3，“GFG-3”，9，2]，temp =“GF”
> **输出** : {'GFG-1': [4，6]，' GFG-2': [3]，' GFG-3': [9，2]}
> **解释**:全部分组直到下一个前缀。
> 
> **输入**:test _ list =[“MRK-1”，4，6，“MRK-2”，3，“MRK-3”，9，2]，temp =“MR”
> **输出**:{‘MRK-1’:[4，6]，‘MRK-2’:[3]，‘MRK-3’:[9，2]}
> **解释**:全部分组直到下一个前缀，“MR”。

**方法:使用 group by()+starts with()+lambda**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 groupby()对所有元素进行前缀分组，lambda 函数有助于对分组进行前缀分离。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert List to key-value list by prefic grouping
# Using groupby() + startswith() + lambda
from itertools import groupby

# initializing list
test_list = ["GFG-1", 4, 6, 7, "GFG-2", 2, 3, "GFG-3", 9, 2, 4, 6]

# printing original list
print("The original list : " + str(test_list))

# initializing prefix 
temp = "GFG"

res = {}
# extracting result from grouped by prefix
for key, val in groupby(test_list, lambda ele: str(ele).startswith(temp)):

    # checking for existing key 
    if key:
        k = next(val)
    else:
        res[k] = list(val)

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```
The original list : ['GFG-1', 4, 6, 7, 'GFG-2', 2, 3, 'GFG-3', 9, 2, 4, 6]
The constructed dictionary : {'GFG-1': [4, 6, 7], 'GFG-2': [2, 3], 'GFG-3': [9, 2, 4, 6]}

```