# Python |将元组值分类到字典值列表中

> 原文:[https://www . geesforgeks . org/python-category-tuple-values-in-dictionary-value-list/](https://www.geeksforgeeks.org/python-categorize-tuple-values-into-dictionary-value-list/)

有时，在使用 Python 时，我们可能会面临这样一个问题，即我们有元组列表形式的数据，我们打算用元组值列表将它们分类到字典中。让我们讨论执行这项任务的某些方法。

**方法一:使用`setdefault()` +循环**
使用`setdefault()`可以轻松执行该任务。在这种情况下，我们只需通过迭代获取元组的键和值对，`setdafault()`用于为字典的相应键赋值。

```py
# Python3 code to demonstrate working of
# Categorize tuple values into dictionary value list
# Using setdefault() + loop

# Initialize list of tuples
test_list = [(1, 3), (1, 4), (2, 3), (3, 2), (5, 3), (6, 4)]

# printing original list
print("The original list : " +  str(test_list))

# Using setdefault() + loop
# Categorize tuple values into dictionary value list
res = {}
for i, j in test_list:
     res.setdefault(j, []).append(i)

# printing result 
print("The dictionary converted from tuple list : " + str(res))
```

**Output :**

> 原始列表:[(1，3)，(1，4)，(2，3)，(3，2)，(5，3)，(6，4)]
> 从元组列表转换而来的字典:{2: [3]，3: [1，2，5]，4: [1，6]}