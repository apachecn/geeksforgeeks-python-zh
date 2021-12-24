# Python |列表中连续元素配对

> 原文:[https://www . geesforgeks . org/python-连续元素-列表配对/](https://www.geeksforgeeks.org/python-consecutive-elements-pairing-in-list/)

有时，在处理列表时，我们需要将列表中相似的元素配对，然后将它们存储为列表列表。这个特殊的任务在许多领域都有它的用处，无论是网络开发还是日常编程。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
列表理解可以很容易地用来执行这个特殊的任务，但是要连续制作第 I 个和第(i+1)个元素对。

```
# Python3 code to demonstrate
# consecutive element pairing 
# using list comprehension

# initializing list
test_list = [5, 4, 1, 3, 2]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# consecutive element pairing 
res = [[test_list[i], test_list[i + 1]]
        for i in range(len(test_list) - 1)]

# print result
print("The consecutive element paired list is : " + str(res))
```

**Output :**

```

The original list : [5, 4, 1, 3, 2]
The consecutive element paired list is : [[5, 4], [4, 1], [1, 3], [3, 2]]

```