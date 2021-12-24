# Python |连接所有记录

> 原文:[https://www . geesforgeks . org/python-concatenate-all-records/](https://www.geeksforgeeks.org/python-concatenate-all-records/)

有时，在处理记录形式的数据时，我们可能会遇到一个问题，即我们需要连接所有接收到的记录的元素。这是数据科学领域中非常常见的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用生成器表达式+ join()**
这是实现解决这个任务最基本的方法。在本文中，我们使用生成器表达式迭代整个嵌套列表，并使用 join()获得串联的元素。

```py
# Python3 code to demonstrate working of
# Concatenate All Records
# using join() + generator expression

# initialize list 
test_list = [('geeksforgeeks ', 'is' ), (' best', ' for'), (' all', ' geeks')]

# printing original list 
print("The original list : " + str(test_list))

# Concatenate All Records
# using join() + generator expression
res = "".join(j for i in test_list for j in i)

# printing result
print("The Concatenated elements of list is : " + res)
```

**Output :**

```py
The original list : [('geeksforgeeks ', 'is'), (' best', ' for'), (' all', ' geeks')]
The Concatenated elements of list is : geeksforgeeks is best for all geeks

```