# Python–将每个列表元素加倍

> 原文:[https://www . geesforgeks . org/python-双-每个-列表-元素/](https://www.geeksforgeeks.org/python-double-each-list-element/)

有时，在处理数据时，我们只有一个简单的应用程序，其中我们需要将列表的内容增加一倍，并使其大小增加 100%。这在网络开发和机器学习领域有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们只需将相同的元素再次添加到该索引元素中，列表的所有内容都会添加到自身中，即增加一倍。

```
# Python3 code to demonstrate 
# Double List
# using loop

# Initializing list
test_list = [12, 67, 98, 34, 43]

# printing original list
print("The original list is : " + str(test_list))

# Double List
# using loop
res = []
for ele in test_list:
    res.append(ele + ele)

# printing result 
print ("Double List is : " + str(res))
```

**Output :**

```
The original list is : [12, 67, 98, 34, 43]
Double List is : [24, 134, 196, 68, 86]

```