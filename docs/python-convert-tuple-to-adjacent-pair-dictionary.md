# Python |将元组转换为相邻对字典

> 原文:[https://www . geesforgeks . org/python-convert-tuple-to-neighbor-pair-dictionary/](https://www.geeksforgeeks.org/python-convert-tuple-to-adjacent-pair-dictionary/)

有时，在处理记录时，我们会遇到一个问题，即我们有数据，需要使用相邻元素转换为键值字典。这个问题可以在 web 开发领域得到应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`dict()` +词典理解+切片**
以上功能可以解决这个问题。在这种情况下，我们只是切片元组的替代部分，并使用字典理解来分配相应的值。使用`dict()`将结果转换为词典。

```
# Python3 code to demonstrate working of
# Convert tuple to adjacent pair dictionary
# using dict() + dictionary comprehension + slicing

# initialize tuple
test_tup = (1, 5, 7, 10, 13, 5)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Convert tuple to adjacent pair dictionary
# using dict() + dictionary comprehension + slicing
res = dict(test_tup[idx : idx + 2] for idx in range(0, len(test_tup), 2))

# printing result
print("Dictionary converted tuple : " + str(res))
```

**Output :**

```
The original tuple : (1, 5, 7, 10, 13, 5)
Dictionary converted tuple : {1: 5, 13: 5, 7: 10}

```