# Python |基于模式在列表中增加 1

> 原文:[https://www . geesforgeks . org/python-increment-1s-in-list-based-on-pattern/](https://www.geeksforgeeks.org/python-increment-1s-in-list-based-on-pattern/)

给定一个二进制数 0 和 1 的列表，编写一个 Python 程序来转换该列表，这样每当 0 序列出现后出现 1 时，就将其增加 n+1，其中“n”是最后一个增量。

**示例:**

```py
Input : [0, 1, 0, 0, 1, 1, 0, 0, 0, 1, 1, 1]
Output : [0, 1, 0, 0, 2, 2, 0, 0, 0, 3, 3, 3]

Input : [1, 0, 1, 0, 0, 0, 1, 1, 0, 0, 1, 1, 1, 0, 1, 0, 1]
Output : [1, 0, 2, 0, 0, 0, 3, 3, 0, 0, 4, 4, 4, 0, 5, 0, 6]

```

**进场#1 :** 幼稚进场

对于给定的问题，这是一种幼稚的方法。它使用两个变量“previous”和“grp”来存储先前递增的数字，并将 1 的数字存储在一个组中。现在，使用 for 循环，相应地增加 1。

```py
# Python3 program to increment 1's in 
# list based on pattern 

def transform(lst):

    previous = 0
    grp = 0
    for elem in lst:
        if elem and not previous:
             grp += 1
        previous = elem
        yield (grp if elem else 0)

# Driver code
lst = [0, 1, 0, 0, 1, 1, 0, 0, 0, 1, 1, 1]
x = (transform(lst))
res = []
for i in range(0, len(lst)):
    res.append(next(x))
print(res)
```

**Output:**

```py
[0, 1, 0, 0, 2, 2, 0, 0, 0, 3, 3, 3]

```

**接近#2 :** 使用*从 *itertools* 模块计数*、*链*和*组。
对于给定的问题，这是一种高效且更加精确的方法，我们使用 *itertools* 模块中的*计数*、*链*和 *groupby* 。*

```py
# Python3 program to increment 1's in 
# list based on pattern 
from itertools import * 

def transform(lst):

    c = count(1)
    return list(chain(*[list(g) if k != 1 else [next(c)]*len(list(g)) 
    for k, g in groupby(lst)]))

# Driver code
lst = [0, 1, 0, 0, 1, 1, 0, 0, 0, 1, 1, 1]
print(transform(lst))
```

**Output:**

```py
[0, 1, 0, 0, 2, 2, 0, 0, 0, 3, 3, 3]

```