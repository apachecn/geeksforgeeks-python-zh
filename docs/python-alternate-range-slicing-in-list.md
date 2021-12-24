# Python |列表中的交替范围切片

> 原文:[https://www . geesforgeks . org/python-alternate-range-slicing-in-list/](https://www.geeksforgeeks.org/python-alternate-range-slicing-in-list/)

列表切片在 Python 中是非常常见的工具，人们可以很容易地从列表中切片某些元素，但有时，我们需要以不连续的方式执行该任务，并切片交替的范围。让我们讨论如何解决这个特殊的问题。

**方法#1:使用列表理解**
列表理解可用于轻松执行该特定任务，因为它可用于运行循环并仅过滤剩余部分超过目标切片大小一半的元素*乘以 2* 。通过这种方法，我们可以交替提取范围内的分片数。

```py
# Python3 code to demonstrate
# alternate range slicing 
# using list comprehension

# initializing list 
test_list = [2, 4, 6, 8, 9, 10, 12, 16, 18, 20, 7, 30]

# printing original list
print("The original list : " + str(test_list))

# Select range size 
N = 3

# using list comprehension
# alternate range slicing
res = [test_list[i] for i in range(len(test_list)) 
                              if i % (N * 2) >= N]

# print result
print("The alternate range sliced list : " + str(res))
```

**Output :**

```py
The original list : [2, 4, 6, 8, 9, 10, 12, 16, 18, 20, 7, 30]
The alternate range sliced list : [8, 9, 10, 20, 7, 30]

```