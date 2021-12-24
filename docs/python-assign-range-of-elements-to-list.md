# Python |将元素范围分配给列表

> 原文:[https://www . geesforgeks . org/python-将元素范围分配给列表/](https://www.geeksforgeeks.org/python-assign-range-of-elements-to-list/)

给列表分配元素是一个常见的问题，在前面的文章中已经讨论了它的许多变种。这篇特别的文章讨论了列表中元素范围的插入。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`extend()`**
这可以使用扩展函数来解决，在扩展函数中，可以使用范围函数在后端插入数字范围。

```
# Python3 code to demonstrate
# Assigning range of elements to List
# using extend()

# initializing list
test_list = [3, 5, 6, 8]

# printing original list
print("The original list : " + str(test_list))

# using extend()
# Assigning range of elements to List
test_list.extend(range(6))

# print result
print("The list after adding range elements : " + str(test_list))
```

**Output :**

```
The original list : [3, 5, 6, 8]
The list after adding range elements : [3, 5, 6, 8, 0, 1, 2, 3, 4, 5]

```