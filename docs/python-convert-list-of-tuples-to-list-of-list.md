# Python |将元组列表转换为列表列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-tuples-to-list/](https://www.geeksforgeeks.org/python-convert-list-of-tuples-to-list-of-list/)

这是一个非常简单的问题，但是由于 python 语言的某些限制，可能会有大量的应用。因为元组是不可变的，所以它们不容易处理，而列表在处理时总是更好的选择。让我们讨论一下将元组列表转换为列表列表的某些方法。

**方法#1:使用列表理解**
使用列表理解很容易做到这一点。我们只是遍历每个列表，将元组转换为列表。

```
# Python3 code to demonstrate
# convert list of tuples to list of list
# using list comprehension

# initializing list 
test_list = [(1, 2), (3, 4), (5, 6)]

# printing original list 
print("The original list of tuples : " + str(test_list))

# using list comprehension
# convert list of tuples to list of list
res = [list(ele) for ele in test_list]

# print result
print("The converted list of list : " + str(res))
```

**Output :**

```
The original list of tuples : [(1, 2), (3, 4), (5, 6)]
The converted list of list : [[1, 2], [3, 4], [5, 6]]

```