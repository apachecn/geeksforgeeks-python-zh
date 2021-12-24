# Python |获取具有相同第一个值的元组的和

> 原文:[https://www . geesforgeks . org/python-get-sum-of-tuples-具有相同的第一值/](https://www.geeksforgeeks.org/python-get-sum-of-tuples-having-same-first-value/)

给定元组列表，任务是对具有相同第一值的元组求和。

**示例:**

```py
Input: [(1, 13), (2, 190), (3, 82), (1, 12)]
Output: [(1, 25), (2, 190), (3, 82)]

Input: [(1, 13), (1, 190), (3, 25), (1, 12)]
Output: [(1, 215), (3, 25)]

```

让我们讨论一下完成这项任务的不同方法。

**方法#1:** 使用`map()`

```py
# Python code to get sum of tuples having same first value

# Initialisation of list of tuple
Input = [(1, 13), (1, 190), (3, 25), (1, 12)]

d = {x:0 for x, _ in Input}

for name, num in Input: d[name] += num

# using map
Output = list(map(tuple, d.items()))

# printing output
print(Output)
```

**Output:**

```py
[(1, 215), (3, 25)]

```

**方法 2:** 使用`defaultdict`

```py
# Python code to sum list of tuples having same first value

# Importing
from collections import defaultdict

# Initialisation of list of tuple
Input = [(2, 190), (1, 13), (1, 12), 
         (2, 14), (3, 82), (1, 70)]

# Initialisation of defaultdict
output = defaultdict(int)

for k, v in Input:
    output[k] += v

# Printing output
print(list(output.items()))
```

**Output:**

```py
[(1, 95), (2, 204), (3, 82)]

```