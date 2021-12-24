# Python |将三重嵌套转换为双嵌套列表

> 原文:[https://www . geesforgeks . org/python-convert-三嵌套-到-双嵌套-list/](https://www.geeksforgeeks.org/python-convert-triple-nesting-to-double-nesting-list/)

有时，在处理列表时，我们可能会遇到需要对嵌套列表进行展平的问题。这种问题已经讨论过很多次了。但有时，展平也可能是从三重嵌套到双重嵌套。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这个任务可以使用列表理解的技巧来执行。在这种情况下，可以只取三重嵌套列表的初始元素，然后将其解包为双重嵌套列表。

```py
# Python3 code to demonstrate working of
# Convert Triple nesting to Double nesting list
# using list comprehension

# initialize list
test_list = [[[1, 4, 6]], [[8, 9, 10, 7]]]

# printing original list
print("The original list is : " + str(test_list))

# Convert Triple nesting to Double nesting list
# using list comprehension
res = [sub[0] for sub in test_list]

# printing result
print("Double nested list from triple nested : " + str(res))
```

**Output :**

```py
The original list is : [[[1, 4, 6]], [[8, 9, 10, 7]]]
Double nested list from triple nested : [[1, 4, 6], [8, 9, 10, 7]]

```