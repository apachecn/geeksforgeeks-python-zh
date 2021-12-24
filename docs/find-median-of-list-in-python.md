# 在 Python 中找到列表的中位数

> 原文:[https://www . geesforgeks . org/find-python 列表中值/](https://www.geeksforgeeks.org/find-median-of-list-in-python/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要找到列表的中位数。这个问题在数学领域和一般计算中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `"~"`运算符**
该任务可以使用上述功能的组合以强力方式执行。在这种情况下，我们对列表进行排序，并通过使用“~”运算符的属性来执行求反，我们从前面和后面访问列表，执行求中值所需的计算。

```py
# Python3 code to demonstrate working of
# Median of list
# Using loop + "~" operator

# initializing list
test_list = [4, 5, 8, 9, 10, 17]

# printing list
print("The original list : " + str(test_list))

# Median of list
# Using loop + "~" operator
test_list.sort()
mid = len(test_list) // 2
res = (test_list[mid] + test_list[~mid]) / 2

# Printing result
print("Median of list is : " + str(res))
```

**Output :**

```py

The original list : [4, 5, 8, 9, 10, 17]
Median of list is : 8.5

```