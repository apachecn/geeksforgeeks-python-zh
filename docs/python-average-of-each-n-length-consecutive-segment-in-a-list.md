# Python |列表中每个 n 长度连续段的平均值

> 原文:[https://www . geesforgeks . org/python-每 n 个长度的平均连续段列表/](https://www.geeksforgeeks.org/python-average-of-each-n-length-consecutive-segment-in-a-list/)

给定一个列表，任务是找到每个 n 长度连续段的平均值，其中每个段包含 n 个元素。

**示例:**

```py
Input : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11,
         12, 13, 14, 15, 16, 17, 18, 19, 20]

Output: [3, 4, 5, 6, 7, 8, 9, 10, 11, 
         12, 13, 14, 15, 16, 17, 18]

Explanation:
Segment 1 - [1, 2, 3, 4, 5] => 15/5 = 3
Segment 2 - [2, 3, 4, 5, 6] => 20/5 = 4
Segment 3 - [3, 4, 5, 6, 7] => 25/5 = 5
and so on..... 
```

**方法#1:** 使用列表理解

```py
# Python code to find average of each consecutive segment

# List initialisation
Input = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11,
         12, 13, 14, 15, 16, 17, 18, 19, 20]

# Defining Splits
splits = 5

# Finding average of each consecutive segment
Output = [sum(Input[i:i + splits])/splits
          for i in range(len(Input) - splits + 1)]

# printing output
print(Output)
```

**Output:**

> [3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0, 10.0, 11.0, 12.0, 13.0, 14.0, 15.0, 16.0, 17.0, 18.0]

**方法 2:** 使用`mean` 功能

```py
# Python code to find average of each consecutive segment

# Importing
from statistics import mean
from itertools import islice

# List initialisation
Input = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11,
         12, 13, 14, 15, 16, 17, 18, 19, 20]

# Finding average of each consecutive segment
zip_list = zip(*(islice(Input, i, None) for i in range(5)))
Output = list(map(mean, zip_list))

# printing output
print(Output)
```

**Output:**

> [3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18]