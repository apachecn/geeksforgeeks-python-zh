# Python–组相邻坐标

> 原文:[https://www . geesforgeks . org/python-group-相邻-坐标/](https://www.geeksforgeeks.org/python-group-adjacent-coordinates/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要对矩阵上相邻的所有坐标进行分组，即水平和垂直距离为 1。这叫做**曼哈滕**距离。这种问题可能发生在竞争性编程领域。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_list = [(4，4)，(6，4)，(7，8)]
> **输出** : [[(7，8)]，[(6，4)]，[(4，4)]
> **输入** : test_list = [(4，4)，(5，4)]
> **输出**:[(5，4)，(4，4)]

**方法:使用 product() + groupby() + list 领悟**
以上方法的组合可以用来解决这个问题。在本文中，我们使用 groupby()执行元素分组任务，并使用 product()检查对。驱动该解决方案的逻辑类似于联合查找算法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Group Adjacent Coordinates
# Using product() + groupby() + list comprehension
from itertools import groupby, product

def Manhattan(tup1, tup2):
    return abs(tup1[0] - tup2[0]) + abs(tup1[1] - tup2[1])

# initializing list
test_list = [(4, 4), (6, 4), (7, 8), (11, 11),
                     (7, 7), (11, 12), (5, 4)]

# printing original list
print("The original list is : " + str(test_list))

# Group Adjacent Coordinates
# Using product() + groupby() + list comprehension
man_tups = [sorted(sub) for sub in product(test_list, repeat = 2)
                                         if Manhattan(*sub) == 1]

res_dict = {ele: {ele} for ele in test_list}
for tup1, tup2 in man_tups:
    res_dict[tup1] |= res_dict[tup2]
    res_dict[tup2] = res_dict[tup1]

res = [[*next(val)] for key, val in groupby(
        sorted(res_dict.values(), key = id), id)]

# printing result
print("The grouped elements : " + str(res))
```

**Output**

```py
The original list is : [(4, 4), (6, 4), (7, 8), (11, 11), (7, 7), (11, 12), (5, 4)]
The grouped elements : [[(6, 4), (5, 4), (4, 4)], [(7, 8), (7, 7)], [(11, 12), (11, 11)]]

```