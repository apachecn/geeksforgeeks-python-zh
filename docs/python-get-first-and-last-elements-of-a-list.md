# Python |获取列表的第一个和最后一个元素

> 原文:[https://www . geesforgeks . org/python-获取列表中的第一个和最后一个元素/](https://www.geeksforgeeks.org/python-get-first-and-last-elements-of-a-list/)

有时，可能需要获取列表中数字的范围，对于这样的应用程序，我们需要获取列表的第一个和最后一个元素。让我们讨论获取列表的第一个和最后一个元素的某些方法。

**方法#1:使用列表索引**
使用主列表中的列表索引可以执行这个特定的任务。这是人们能想到的完成这一特殊任务的最天真的方法。

```py
# Python3 code to demonstrate 
# to get first and last element of list
# using list indexing

# initializing list 
test_list = [1, 5, 6, 7, 4]

# printing original list 
print ("The original list is : " +  str(test_list))

# using list indexing
# to get first and last element of list
res = [ test_list[0], test_list[-1] ] 

# printing result
print ("The first and last element of list are : " +  str(res))
```

**Output:**

```py
The original list is : [1, 5, 6, 7, 4]
The first and last element of list are : [1, 4]

```