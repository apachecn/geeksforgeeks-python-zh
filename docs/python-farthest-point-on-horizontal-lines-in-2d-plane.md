# Python | 2D 平面水平线最远点

> 原文:[https://www . geesforgeks . org/python-2d 平面水平线最远点/](https://www.geeksforgeeks.org/python-farthest-point-on-horizontal-lines-in-2d-plane/)

有时，在竞争性编程中，我们可能会面临一个几何领域的问题，并且使用 x-y 坐标系。元组列表可用于存储相同的内容。除此之外，还有一个问题，我们需要 x 轴最大值与 y 轴相似的点，即水平线上最远的点。让我们讨论讨论这个问题的某些方法。

**方法:使用列表理解+ `max()`**
这是一种通用的蛮力方法，用于获取公共 y 轴的最大 x 轴点，使用列表理解制作为 1 个直线。`max()`用来求 x 轴元素的最大值。

```py
# Python3 code to demonstrate working of
# Farthest point on horizontal lines in 2D plane
# Using list comprehension + max()
from collections import defaultdict

# initializing list
test_list = [(1, 6), (4, 6), (2, 6), (6, 8), (1, 8), (2, 9)]

# printing original list
print("The original list is : " +  str(test_list))

# Using list comprehension + max()
# Farthest point on horizontal lines in 2D plane
temp = defaultdict(list)
for key, val in test_list:
   temp[val].append(key)
res = [(key, val) for key, val in test_list if max(temp[val]) == key]

# Printing result
print("The list after filtering just maximum points on lines : " +  str(res))
```

**Output :**

```py
The original list is : [(1, 6), (4, 6), (2, 6), (6, 8), (1, 8), (2, 9)]
The list after filtering just maximum points on lines : [(4, 6), (6, 8), (2, 9)]

```