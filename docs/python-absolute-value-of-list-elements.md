# Python |列表元素绝对值

> 原文:[https://www . geesforgeks . org/python-元素列表绝对值/](https://www.geeksforgeeks.org/python-absolute-value-of-list-elements/)

有时，在使用 Python 列表时，我们需要找到绝对数量，即列表中具有正数量级的所有元素。这个问题在数据科学的各个领域都有应用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用列表理解+ `abs()`**
这个任务可以使用列表理解技术来执行，在该技术中，我们只需迭代每个元素，并使用`abs()`不断找到它的绝对值。

```py
# Python3 code to demonstrate working of
# Absolute value of list elements
# using abs() + list comprehension

# initialize list
test_list = [5, -6, 7, -8, -10]

# printing original list
print("The original list is : " + str(test_list))

# Absolute value of list elements
# using abs() + list comprehension
res =  [abs(ele) for ele in test_list]

# printing result
print("Absolute value list : " + str(res))
```

**Output :**

```py
The original list is : [5, -6, 7, -8, -10]
Absolute value list : [5, 6, 7, 8, 10]

```