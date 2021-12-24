# Python–在列表中找到最小元素的索引

> 原文:[https://www . geesforgeks . org/python-查找列表中最小元素的索引/](https://www.geeksforgeeks.org/python-find-the-index-of-minimum-element-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们打算找到列表的最小元素的位置。这个任务很容易，讨论了很多次。但有时，我们可以有多个最小元素，从而有多个最小位置。让我们讨论完成这项任务的方法。

**方法#1:使用`min() + enumerate()` +列表理解**
在该方法中，上述功能的组合用于执行该特定任务。这分两步进行。在第一步中，我们获取最小元素，然后使用列表理解来访问列表，并使用枚举来访问对应的元素，并提取与步骤 1 中处理的最小元素相等的每个元素位置。

```
# Python3 code to demonstrate working of
# Minimum element indices in list
# Using list comprehension + min() + enumerate()

# initializing list
test_list = [2, 5, 6, 2, 3, 2]

# printing list
print("The original list : " + str(test_list))

# Minimum element indices in list
# Using list comprehension + min() + enumerate()
temp = min(test_list)
res = [i for i, j in enumerate(test_list) if j == temp]

# Printing result
print("The Positions of minimum element : " + str(res))
```

**Output :**

```
The original list : [2, 5, 6, 2, 3, 2]
The Positions of minimum element : [0, 3, 5]

```