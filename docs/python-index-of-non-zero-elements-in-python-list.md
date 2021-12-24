# Python | Python 列表中非零元素的索引

> 原文:[https://www . geesforgeks . org/python-非零元素索引-python-list/](https://www.geeksforgeeks.org/python-index-of-non-zero-elements-in-python-list/)

有时，在使用 python 列表时，我们可能会遇到一个问题，即我们需要找到除 0 之外的所有整数的位置。这可以应用于日常编程或竞争性编程。让我们讨论一下执行这项特殊任务的速记方法。

**方法:使用`enumerate()` +列表理解**
该方法可以使用功能组合来执行。在这种情况下，我们使用枚举函数一起访问索引元素，并使用列表理解进行迭代和逻辑创建。

```
# Python3 code to demonstrate working of
# Index of Non-Zero elements in Python list
# using list comprehension + enumerate()

# initialize list
test_list = [6, 7, 0, 1, 0, 2, 0, 12]

# printing original list
print("The original list is : " + str(test_list))

# Index of Non-Zero elements in Python list
# using list comprehension + enumerate()
res = [idx for idx, val in enumerate(test_list) if val != 0]

# printing result
print("Indices of Non-Zero elements : " + str(res))
```

**Output :**

```
The original list is : [6, 7, 0, 1, 0, 2, 0, 12]
Indices of Non-Zero elements : [0, 1, 3, 5, 7]

```