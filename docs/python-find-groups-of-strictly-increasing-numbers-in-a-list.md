# Python |在列表中查找严格递增的数字组

> 原文:[https://www . geeksforgeeks . org/python-查找列表中严格递增的数字组/](https://www.geeksforgeeks.org/python-find-groups-of-strictly-increasing-numbers-in-a-list/)

给定一个整数列表，编写一个 Python 程序来查找严格递增的数字组。

**示例:**

```
Input : [1, 2, 3, 5, 6]
Output : [[1, 2, 3], [5, 6]]

Input : [8, 9, 10, 7, 8, 1, 2, 3]
Output : [[8, 9, 10], [7, 8], [1, 2, 3]]

```

**方法#1 :** 皮托尼天真

这是一种使用额外输入列表空间的幼稚方法。它使用 for 循环，并且在每次迭代中，它检查下一个元素是否从前一个元素递增 1。如果是，将其附加到当前子列表，否则，创建另一个子列表。

```
# Python3 program to Find groups 
# of strictly increasing numbers within 

def groupSequence(lst):
    res = [[lst[0]]]

    for i in range(1, len(lst)):
        if lst[i-1]+1 == lst[i]:
            res[-1].append(lst[i])

        else:
            res.append([lst[i]])
    return res

# Driver program 
l = [8, 9, 10, 7, 8, 1, 2, 3]
print(groupSequence(l))
```

**Output:**

```
[[8, 9, 10], [7, 8], [1, 2, 3]]

```

**进场#2 :** 交替幼稚

这是上述天真方法的替代方案。这个方法相当简单直接。它构造了一个*开始 _ 界限*列表和一个*结束 _ 界限*列表，其中包含递增整数的开始和结束序列的位置。因此只需使用 for 循环返回边界。

```
# Python3 program to Find groups 
# of strictly increasing numbers within 

def groupSequence(l):
    start_bound = [i for i in range(len(l)-1)
        if (l == 0 or l[i] != l[i-1]+1)
        and l[i + 1] == l[i]+1]

    end_bound = [i for i in range(1, len(l))
        if l[i] == l[i-1]+1 and
        (i == len(l)-1 or l[i + 1] != l[i]+1)]

    return [l[start_bound[i]:end_bound[i]+1]
    for i in range(len(start_bound))]

# Driver program 
l = [8, 9, 10, 7, 8, 1, 2, 3]
print(list(groupSequence(l)))
```

**Output:**

```
[[8, 9, 10], [7, 8], [1, 2, 3]]

```

**方法#3 :** 使用可迭代并产生
这种方法使用另一个列表“res”和一个可迭代的“it”。变量“prev”用于保存前一个整数的记录，start 用于获取递增序列的起始位置。使用循环，在每次迭代中，我们检查 start 元素是否是 prev 的后继元素。如果是，我们将其附加到 res，否则，我们只需将 res + [prev]作为 list 元素。

```
# Python3 program to Find groups 
# of strictly increasing numbers within 

def groupSequence(x):
    it = iter(x)
    prev, res = next(it), []

    while prev is not None:
        start = next(it, None)

        if prev + 1 == start:
            res.append(prev)
        elif res:
            yield list(res + [prev])
            res = []
        prev = start

# Driver program 
l = [8, 9, 10, 7, 8, 1, 2, 3]
print(list(groupSequence(l)))
```

**Output:**

```
[[8, 9, 10], [7, 8], [1, 2, 3]]

```

**方法#4 :** 使用 itertools
Python itertools 提供了循环和 groupby 等操作，这些操作在该方法中使用。首先，我们使用循环形成另一个列表“*临时列表*”。循环生成一系列无限重复的值。然后我们使用 groupby 操作对 *temp_list* 进行相应的分组，最终得到所需的输出。

```
# Python3 program to Find groups 
# of strictly increasing numbers within 
from itertools import groupby, cycle

def groupSequence(l):
    temp_list = cycle(l)

    next(temp_list)
    groups = groupby(l, key = lambda j: j + 1 == next(temp_list))
    for k, v in groups:
        if k:
            yield tuple(v) + (next((next(groups)[1])), )

# Driver program 
l = [8, 9, 10, 7, 8, 1, 2, 3]
print(list(groupSequence(l)))
```

**Output:**

```
[(8, 9, 10), (7, 8), (1, 2, 3)]

```