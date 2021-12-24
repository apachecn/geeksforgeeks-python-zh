# Python–矩阵中的连续行求和

> 原文:[https://www . geesforgeks . org/python-连续行-矩阵求和/](https://www.geeksforgeeks.org/python-consecutive-row-summation-in-matrix/)

这篇特别的文章集中在一个在竞争和日常编程中都有用的问题上。有时，当与下一个列表进行比较时，我们需要得到相似索引之间的总和。返回该索引中相似元素之间的总和。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum() + abs() + zip()` +列表理解**
这个特殊问题也可以通过以上 4 个操作的组合来解决。在这里，zip 函数完成了配对列表和配对 sum 的相似索引的双重任务，sum 由 abs 函数计算，然后使用 sum 函数找到 sum，所有这些都受列表理解的限制。

```py
# Python3 code to demonstrate
# Consecutive Row summation in Matrix
# using sum() + abs() + zip() + list comprehension

# initializing list 
test_list = [[3, 4, 5], [4, 6, 8], [1, 9, 2], [3, 7, 10]]

# printing original list 
print("The original list : " + str(test_list))

# using sum() + abs() + zip() + list comprehension
# Consecutive Row summation in Matrix
res = [sum(abs(i + j) for i, j in zip(*ele)) for ele in zip(test_list, test_list[1:])]

# print result
print("The row summation sublist : " + str(res))
```

**Output :**

```py
The original list : [[3, 4, 5], [4, 6, 8], [1, 9, 2], [3, 7, 10]]
The row summation sublist : [30, 30, 32]

```