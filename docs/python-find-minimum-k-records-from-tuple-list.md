# Python–从元组列表中找到最小 k 条记录

> 原文:[https://www . geesforgeks . org/python-find-minimum-k-records-from-tuple-list/](https://www.geeksforgeeks.org/python-find-minimum-k-records-from-tuple-list/)

有时，在处理数据时，我们会遇到一个问题，我们有记录，我们需要从中找到最低的 K 分数。这种应用在 web 开发领域非常流行。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 `sorted()`+λ**
上述功能的组合可用于执行该特定任务。在这种情况下，我们只使用排序函数，并使用列表切片打印最低的 K 个元素。

```
# Python3 code to demonstrate working of
# Minimum K records
# Using sorted() + lambda

# Initializing list 
test_list = [('Manjeet', 10), ('Akshat', 4), ('Akash', 2), ('Nikhil', 8)]

# Initializing K
K = 2

# printing original list
print("The original list is : " + str(test_list))

# Minimum K records
# Using sorted() + lambda
res = sorted(test_list, key = lambda x: x[1])[:K]

# printing result
print("The lowest K records are : " + str(res))
```

**Output :**

```
The original list is : [('Manjeet', 10), ('Akshat', 4), ('Akash', 2), ('Nikhil', 8)]
The lowest K records are : [('Akash', 2), ('Akshat', 4)]

```