# Python |将第 n 个元素插入到其他列表的第 k 个元素中

> 原文:[https://www . geesforgeks . org/python-insert-n th-element-to-kth-element-in-other-list/](https://www.geeksforgeeks.org/python-insert-nth-element-to-kth-element-in-other-list/)

有时，在使用 Python 列表时，可能会出现一个问题，即我们需要执行元素的列表间转换。解决这个问题总是非常有用的。让我们讨论一下执行这项任务的具体方法。

**方法:使用`pop() + insert() + index()`**
该特定任务可以使用上述功能的组合来执行。在这种情况下，我们只是使用 pop 函数的属性来返回和移除元素，并使用索引函数将其插入到其他列表的特定位置。

```py
# Python3 code to demonstrate working of
# Insert Nth element to Kth element in other list
# Using pop() + index() + insert()

# initializing lists
test_list1 = [4, 5, 6, 7, 3, 8]
test_list2 = [7, 6, 3, 8, 10, 12]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing N 
N = 5

# initializing K 
K = 3

# Using pop() + index() + insert()
# Insert Nth element to Kth element in other list
res = test_list1.insert(K, test_list2.pop(N))

# Printing result
print("The list 1 after insert is : " + str(test_list1))
print("The list 2 after remove is : " + str(test_list2))
```

**Output :**

```py
The original list 1 is : [4, 5, 6, 7, 3, 8]
The original list 2 is : [7, 6, 3, 8, 10, 12]
The list 1 after insert is : [4, 5, 6, 12, 7, 3, 8]
The list 2 after remove is : [7, 6, 3, 8, 10]

```