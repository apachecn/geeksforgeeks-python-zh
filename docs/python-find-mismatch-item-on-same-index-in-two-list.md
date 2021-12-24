# Python |在两个列表中的同一索引上查找不匹配项

> 原文:[https://www . geesforgeks . org/python-find-mismatch-同索引双列表上的项目/](https://www.geeksforgeeks.org/python-find-mismatch-item-on-same-index-in-two-list/)

给定两个整数列表，任务是找到两个列表元素不匹配的索引。

```py
Input:
Input1 = [1, 2, 3, 4]
Input2 = [1, 5, 3, 6]

Output: [1, 3]
Explanation:
At index=1 we have 2 and 5 and at index=3
we have 4 and 6 which mismatches.
```

下面是一些实现这个任务的方法。
**方法#1:使用迭代**

## 蟒蛇 3

```py
# Python code to find the index at which the
# element of two list doesn't match.

# List initialisation
Input1 = [1, 2, 3, 4]
Input2 = [1, 5, 3, 6]

# Index initialisation
y = 0

# Output list initialisation
Output = []

# Using iteration to find
for x in Input1:
    if x != Input2[y]:
        Output.append(y)
    y = y + 1

# Printing output
print(Output)
```

**Output:** 

```py
[1, 3]
```