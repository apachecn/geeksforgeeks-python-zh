# Python |分隔字符串列表到字符串矩阵

> 原文:[https://www . geesforgeks . org/python-分隔字符串-列表-字符串-矩阵/](https://www.geeksforgeeks.org/python-delimited-string-list-to-string-matrix/)

有时，在使用 Python 字符串时，我们可能会遇到这样的问题，即需要将字符串列表转换为字符串矩阵，字符串列表中的字符串由 delimiter 连接，而字符串矩阵则由 delimiter 分离。让我们讨论执行这项任务的某些方法。

**方法#1:使用`loop + split()`**
这是可以执行该任务的方式之一。在本文中，我们对每个字符串进行迭代，并使用 split()执行拆分。

```
# Python3 code to demonstrate working of 
# Delimited String List to String Matrix
# Using loop + split()

# initializing list
test_list = ['gfg:is:best', 'for:all', 'geeks:and:CS']

# printing original list
print("The original list is : " + str(test_list))

# Delimited String List to String Matrix
# Using loop + split()
res = []
for sub in test_list:
    res.append(sub.split(':'))

# printing result 
print("The list after conversion : " + str(res)) 
```

**Output :**

```
The original list is : ['gfg:is:best', 'for:all', 'geeks:and:CS']
The list after conversion : [['gfg', 'is', 'best'], ['for', 'all'], ['geeks', 'and', 'CS']]

```