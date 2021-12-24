# Python–连续三元素配对

> 原文:[https://www . geeksforgeeks . org/python-连续-三元素-配对/](https://www.geeksforgeeks.org/python-consecutive-triple-element-pairing/)

有时，在处理列表时，我们需要将列表中的相似元素进行三重配对，然后将它们存储为列表的列表。这个特殊的任务在许多领域都有它的用处，无论是网络开发还是日常编程。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
列表理解可以很容易地用来执行这个特殊的任务，但是要连续制作第 I 个、(i+1)个和(i+2)个元素对。

```py
# Python3 code to demonstrate
# Consecutive Triple element pairing
# using list comprehension

# initializing list
test_list = [5, 4, 1, 3, 2]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# Consecutive Triple element pairing
res = [[test_list[i], test_list[i + 1], test_list[i + 2]] for i in range(len(test_list) - 2)]

# print result
print("The consecutive element triple paired list is : " + str(res))
```

**Output :**

```py
The original list : [5, 4, 1, 3, 2]
The consecutive element triple paired list is : [[5, 4, 1], [4, 1, 3], [1, 3, 2]]

```