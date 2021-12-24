# Python |将整型列表转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-integer-list-to-tuple-list/](https://www.geeksforgeeks.org/python-convert-integral-list-to-tuple-list/)

有时候，在处理数据时，我们会遇到一个问题，那就是我们需要执行数据类型的相互转换。可能会有一个问题，我们可能需要将整数列表元素转换为单元素元组。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
列表理解可以作为解决这个特定问题的速记方法。在本文中，我们遍历列表，并将每个整数元素转换为一个元组对象。

```py
# Python3 code to demonstrate working of
# Convert Integral list to tuple list
# using list comprehension

# initialize list 
test_list = [1, 4, 6, 8, 9]

# printing original list 
print("The original list : " + str(test_list))

# Convert Integral list to tuple list
# using list comprehension
res = [(ele, ) for ele in test_list]

# printing result
print("List after conversion to tuple list : " + str(res))
```

**Output :**

> 原列表:[1，4，6，8，9]
> 列表转换为元组列表后:[(1)、(4)、(6)、(8)、(9、]