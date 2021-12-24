# Python |在每个子列表中查找最大值

> 原文:[https://www . geesforgeks . org/python-find-每个子列表中的最大值/](https://www.geeksforgeeks.org/python-find-maximum-value-in-each-sublist/)

给定 Python 中的列表列表，编写一个 Python 程序来找到列表每个子列表的最大值。

**示例:**

```
Input : [[10, 13, 454, 66, 44], [10, 8, 7, 23]]
Output :  [454, 23]

Input : [[15, 12, 27, 1, 33], [101, 58, 77, 23]]
Output :  [33, 101]
```

**方法一:**使用列表理解。

```
# Python code to Find maximum of list in nested list

# Initialising List
a = [[10, 13, 454, 66, 44], [10, 8, 7, 23]]

# find max in list
b = [max(p) for p in a]

# Printing max
print(b)
```

**Output:**

```
[454, 23]

```

**方法 2:** 使用`map`

```
# Python code to Find maximum of list in nested list

# Initialising List
a = [[10, 13, 454, 66, 44], [10, 8, 7, 23]]

# find max in list
ans = list(map(max, a))

# Printing max
print(ans)
```

**Output:**

```
[454, 23]

```