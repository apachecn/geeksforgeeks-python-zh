# Python |列表中常见元素的计数

> 原文:[https://www . geesforgeks . org/python-列表中常见元素的计数/](https://www.geeksforgeeks.org/python-count-of-common-elements-in-the-lists/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们必须比较两个列表的索引相似性，因此可能会有计算相等索引对的任务。让我们讨论执行这项任务的某些方法。

**方法#1:使用 `sum() + zip()`**
可以通过将执行两个列表相互映射任务的`zip()`传递给根据相等指数计算总和的`sum()`来执行该任务。

```
# Python3 code to demonstrate working of
# Identical element summation in lists
# using sum() + zip()

# initialize lists
test_list1 = [5, 6, 10, 4, 7, 1, 19]
test_list2 = [6, 6, 10, 3, 7, 10, 19]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Identical element summation in lists
# using sum() + zip()
res = sum(x == y for x, y in zip(test_list1, test_list2))

# printing result
print("Summation of Identical elements : " + str(res))
```

**Output :**

```
The original list 1 is : [5, 6, 10, 4, 7, 1, 19]
The original list 2 is : [6, 6, 10, 3, 7, 10, 19]
Summation of Identical elements : 4

```