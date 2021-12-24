# Python–列表间对角元素添加

> 原文:[https://www . geesforgeks . org/python-对角线-元素-列表间添加/](https://www.geeksforgeeks.org/python-diagonal-element-addition-among-lists/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要以对角线方式执行列表的添加，即将 1 个列表的 i + 1 个元素添加到其他列表的 I+1 个元素中。这种问题可以在日常编程中应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们迭代一个列表，测试添加另一个列表的第 I+1 个元素，并构造结果列表。

```py
# Python3 code to demonstrate 
# Diagonal element addition among lists
# using loop

# Initializing lists
test_list1 = [1, 6, 8, 5, 3]
test_list2 = [8, 10, 3, 4, 5]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Diagonal element addition among lists
# using loop
res = []
for idx in range(0, len(test_list1) - 1):
    res.append(test_list1[idx] + test_list2[idx + 1])

# printing result 
print ("List after diagonal addition : " + str(res))
```

**Output :**

```py
The original list 1 is : [1, 6, 8, 5, 3]
The original list 2 is : [8, 10, 3, 4, 5]
List after diagonal addition : [11, 9, 12, 10]

```