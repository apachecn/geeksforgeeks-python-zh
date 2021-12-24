# Python |列表中连续最大出现次数

> 原文:[https://www . geeksforgeeks . org/python-连续-列表中最大出现次数/](https://www.geeksforgeeks.org/python-consecutive-maximum-occurrence-in-list/)

有时，在使用 Python 列表或在竞争性编程设置中，我们会遇到一个子问题，在这个子问题中，我们需要获得一个具有最大连续出现次数的元素。关于它的解决方案的知识可以有很大的帮助，并且可以在任何需要的时候使用。让我们讨论执行这项任务的某些方法。

**方法一:使用`groupby() + max()` + lambda**
这个任务可以结合以上功能来解决。在这种情况下，我们使用`groupby()`对数字的每次出现进行分组，并使用`max()`获得最大值。lambda 函数提供了执行该任务实用逻辑。

```
# Python3 code to demonstrate working of
# Consecutive Maximum Occurrence in list
# using groupby() + max() + lambda
from itertools import groupby

# initializing list
test_list = [1, 1, 1, 2, 2, 4, 2, 2, 5, 5, 5, 5]

# printing original list
print("The original list is : " + str(test_list))

# Consecutive Maximum Occurrence in list
# using groupby() + max() + lambda
temp = groupby(test_list)
res = max(temp, key = lambda sub: len(list(sub[1])))

# printing result 
print("Maximum Consecutive Occurring number is : " + str(res[0]))
```

**Output :**

```
The original list is : [1, 1, 1, 2, 2, 4, 2, 2, 5, 5, 5, 5]
Maximum Consecutive Occurring number is : 5

```