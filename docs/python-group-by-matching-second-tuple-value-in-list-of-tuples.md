# 通过匹配元组列表中的第二个元组值进行 Python 分组

> 原文:[https://www . geesforgeks . org/python-按匹配分组-第二元组-元组列表中的值/](https://www.geeksforgeeks.org/python-group-by-matching-second-tuple-value-in-list-of-tuples/)

给定元组列表，任务是通过匹配元组中的第二个元素来对元组进行分组。我们可以通过使用字典检查每个元组中的第二个元素来实现这一点。

**示例:**

```py
Input : [(20, 80), (31, 80), (1, 22), (88, 11), (27, 11)]
Output: {80: [(20, 80), (31, 80)],
         11: [(88, 11), (27, 11)],
         22: [(1, 22)]}

Input : [(20, 'Geek'), (31, 'Geek'), (88, 'NotGeek'), (27, 'NotGeek')]
Output: {'NotGeek': [(88, 'NotGeek'), (27, 'NotGeek')],
         'Geek': [(20, 'Geek'), (31, 'Geek')]}

```

**代码#1:**

```py
# Python program to group tuples by matching 
# second tuple value in list of tuples

# Initialisation 
Input = [(20, 80), (31, 80), (1, 22), (88, 11), (27, 11)]

Output = {}
for x, y in Input:
    if y in Output:
        Output[y].append((x, y))
    else:
        Output[y] = [(x, y)]

# Printing Output
print(Output)
```

**Output:**

```py
{80: [(20, 80), (31, 80)], 11: [(88, 11), (27, 11)], 22: [(1, 22)]}

```

**代码#2:**

```py
# Python program to group tuples by matching 
# second tuple value in list of tuples

# Initialisation 
Input = [(20, 'Geek'), (31, 'Geek'), (88, 'NotGeek'), (27, 'NotGeek')]

Output = {}
for x, y in Input:
    if y in Output:
        Output[y].append((x, y))
    else:
        Output[y] = [(x, y)]

# Printing Output
print(Output)
```

**Output:**

```py
{'NotGeek': [(88, 'NotGeek'), (27, 'NotGeek')],
 'Geek': [(20, 'Geek'), (31, 'Geek')]}

```