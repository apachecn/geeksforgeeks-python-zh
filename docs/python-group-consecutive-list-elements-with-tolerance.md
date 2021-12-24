# Python |用公差分组连续列表元素

> 原文:[https://www . geesforgeks . org/python-group-continuous-list-elements-with-tolerance/](https://www.geeksforgeeks.org/python-group-consecutive-list-elements-with-tolerance/)

有时，我们可能需要根据列表中的连续元素对列表进行分组。但是这种情况的一个有用的变体也可以是我们需要考虑容差水平的情况，即允许数字之间的跳跃值，并且不完全连续，但是允许数字之间有“间隙”。让我们讨论一种可以执行该任务的方法。

**方法:使用**发生器
的蛮法来执行这个任务。使用循环和生成器，可以执行此任务。产量操作员负责切片，因此这个问题也可以通过一个小的公差检查来解决。

```py
# Python3 code to demonstrate working of
# Group consecutive list elements with tolerance
# Using generator

# helper generator
def split_tol(test_list, tol):
    res = []
    last = test_list[0]
    for ele in test_list:
        if ele-last > tol:
            yield res
            res = []
        res.append(ele)
        last = ele
    yield res

# initializing list
test_list = [1, 2, 4, 5, 9, 11, 13, 24, 25, 26, 28]

# printing original list
print("The original list is : " + str(test_list))

# Group consecutive list elements with tolerance
# Using generator
res = list(split_tol(test_list, 2))

# printing result 
print("The splitted list is : " + str(res))
```

**Output :**

```py
The original list is : [1, 2, 4, 5, 9, 11, 13, 24, 25, 26, 28]
The splitted list is : [[1, 2, 4, 5], [9, 11, 13], [24, 25, 26, 28]]

```