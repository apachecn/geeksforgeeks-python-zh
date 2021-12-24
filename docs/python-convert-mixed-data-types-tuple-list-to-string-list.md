# Python |将混合数据类型元组列表转换为字符串列表

> 原文:[https://www . geesforgeks . org/python-convert-mixed-data-type-tuple-list-to-string-list/](https://www.geeksforgeeks.org/python-convert-mixed-data-types-tuple-list-to-string-list/)

有时，在处理记录时，我们可能会遇到一个问题，需要将所有记录类型转换为字符串的特定格式。这种问题可能发生在许多领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `tuple() + str()` +生成器表达式**
以上功能的组合可以用来执行这个任务。在本文中，我们使用生成表达式提取每个元组元素，并使用 str()执行转换。对每个元组的迭代是通过列表理解来完成的。

```
# Python3 code to demonstrate working of
# Convert tuple mixed list to string list
# using list comprehension + tuple() + str() + generator expression

# initialize list 
test_list = [('gfg', 1, True), ('is', False), ('best', 2)]

# printing original list 
print("The original list : " + str(test_list))

# Convert tuple mixed list to string list
# using list comprehension + tuple() + str() + generator expression
res = [tuple(str(ele) for ele in sub) for sub in test_list]

# printing result
print("The tuple list after conversion : " + str(res))
```

**Output :**

```
The original list : [('gfg', 1, True), ('is', False), ('best', 2)]
The tuple list after conversion : [('gfg', '1', 'True'), ('is', 'False'), ('best', '2')]

```