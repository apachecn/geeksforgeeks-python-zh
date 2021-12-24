# Python |查找列表中所有元素计数

> 原文:[https://www . geesforgeks . org/python-find-all-elements-count-in-list/](https://www.geeksforgeeks.org/python-find-all-elements-count-in-list/)

获取列表的长度是一个很常见的问题，已经被处理和讨论了很多次，但是有时，我们需要改进它并找到元素的总数，即也包括嵌套列表的元素。让我们试着计算总数，解决这个特殊的问题。

**方法#1:使用列表理解+ `len()`**
我们可以使用列表理解来解决这个问题，作为我们可能用来执行这个特定任务的常规循环的潜在速记。我们只是迭代和计数嵌套列表，最后使用 len 函数返回累计计数。

```py
# Python3 code to demonstrate
# count of all the elements in list 
# Using list comprehension

# initializing list
test_list = [[1, 4, 5], [7, 3], [4], [46, 7, 3]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# count of all the elements in list
res = len([ele for sub in test_list for ele in sub])

# print result
print("The total element count in lists is : " + str(res))
```

**Output :**

```py
The original list : [[1, 4, 5], [7, 3], [4], [46, 7, 3]]
The total element count in lists is : 9

```