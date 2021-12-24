# Python–计数元组列表中的元素

> 原文:[https://www . geesforgeks . org/python-count-elements-in-tuple-list/](https://www.geeksforgeeks.org/python-count-elements-in-tuple-list/)

有时，在处理记录形式的数据时，我们可能会遇到一个问题，即我们需要找到收到的所有记录的计数。这是数据科学领域中非常常见的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`len()` +生成器表达式**
这是实现解决这个任务最基本的方法。在本文中，我们使用生成器表达式迭代整个嵌套列表，并使用 len()获得计数。

```
# Python3 code to demonstrate working of
# Tuple list elements count
# using len() + generator expression

# initialize list 
test_list = [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]

# printing original list 
print("The original list : " + str(test_list))

# Tuple list elements count
# using len() + generator expression
temp = list((int(j) for i in test_list for j in i))
res = len(temp)

# printing result
print("The tuple list elements count : " + str(res))
```

**Output :**

```
The original list : [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]
The tuple list elements count : 10

```