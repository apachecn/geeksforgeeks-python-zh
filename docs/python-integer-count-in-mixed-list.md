# Python |混合列表中的整数计数

> 原文:[https://www . geesforgeks . org/python-混合列表中的整数计数/](https://www.geeksforgeeks.org/python-integer-count-in-mixed-list/)

python 中的列表可以处理不同类型的数据类型。这种列表的操作很复杂。有时我们会遇到一个问题，我们需要找到整数值的计数，其中列表可以包含字符串作为数据类型，即异构的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `len() + isinstance()`**
这个特殊的问题可以通过使用 isinstance 方法过滤我们对 len 的搜索来解决，我们可以过滤掉整数值，然后可以使用 len 函数来获得所需的长度值。

```py
# Python3 code to demonstrate 
# Integer count in Mixed List
# using list comprehension + len() + isinstance()

# initializing list
test_list = [3, 'computer', 5, 'geeks', 6, 7]

# printing original list 
print ("The original list is : " + str(test_list))

# using list comprehension + len() + isinstance()
# Integer count in Mixed List
res = len(list(i for i in test_list if isinstance(i, int)))

# printing result
print ("The length of integers in list is : " + str(res))
```

**Output :**

```py
The original list is : [3, 'computer', 5, 'geeks', 6, 7]
The length of integers in list is : 4

```