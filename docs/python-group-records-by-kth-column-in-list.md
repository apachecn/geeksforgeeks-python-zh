# Python–按列表中的第 k 列分组记录

> 原文:[https://www . geesforgeks . org/python-group-records-by-kth-列表中的列/](https://www.geeksforgeeks.org/python-group-records-by-kth-column-in-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要根据某些参数对记录进行分组。一个这样的参数可以在元组的第 Kth 元素上。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `defaultdict()`**
以上方法的组合可以用来执行这个任务。在本文中，我们使用 defaultdict 在 Kth Column 的基础上将元组存储在不同的列表中，并使用循环进行迭代。

```py
# Python3 code to demonstrate 
# Group records by Kth column in List
# using loop + defaultdict()
from collections import defaultdict

# Initializing list
test_list = [('Gfg', 1), ('is', 2), ('Gfg', 3), ('is', 4), ('best', 5)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 0

# Group records by Kth column in List
# using loop + defaultdict()
temp = defaultdict(list)
for ele in test_list:
    temp[ele[K]].append(ele)
res = list(temp.values())

# printing result 
print ("The list after grouping : " + str(res))
```

**Output :**

```py
The original list is : [('Gfg', 1), ('is', 2), ('Gfg', 3), ('is', 4), ('best', 5)]
The list after grouping : [[('Gfg', 1), ('Gfg', 3)], [('is', 2), ('is', 4)], [('best', 5)]]

```