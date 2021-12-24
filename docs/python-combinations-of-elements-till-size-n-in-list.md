# Python |列表中大小为 N 的元素组合

> 原文:[https://www . geeksforgeeks . org/python-元素组合-直到列表中的大小 n/](https://www.geeksforgeeks.org/python-combinations-of-elements-till-size-n-in-list/)

已经讨论了寻找特定大小的列表元素的组合的问题。但是有时，我们需要更多，我们希望拥有所有大小元素的所有组合，直到 n。让我们讨论一下可以执行该功能的某些方法。

**方法一:使用列表理解+ `combinations()`**
这个任务可以使用列表理解来执行，列表理解可以执行改变组合长度的任务，`combination()`可以执行寻找组合的实际任务。

```
# Python3 code to demonstrate working of
# Combinations of elements till size N in list
# Using list comprehension + combinations()
from itertools import combinations

# initializing list
test_list = [4, 5, 6, 7, 3, 8]

# printing original list
print("The original list is : " +  str(test_list))

# Combinations of elements till size N in list
# Using list comprehension + combinations()
res = [com for sub in range(3) for com in combinations(test_list, sub + 1)]

# Printing result
print("The combinations of elements till length N : " +  str(res))
```

**Output :**

> 原列表为:【4、5、6、7、3、8】
> 长度为 N 的元素组合:【(4)、(5)、(6)、(7)、(3)、(8)、(4、5)、(4、6)、(4、7)、(4、3)、(4、8)、(4、7)、(4、3)、(4、8)、(5、6)、(5、7)、(5、3)、(5、8)、(6、7)、(6、3)、(6、8)、(7)、(6、8)、(7、3)、(7、8)、(3、8)、(4、5、6)、(4、5、7)、(7)、(8) 6, 8), (4, 7, 3), (4, 7, 8), (4, 3, 8), (5, 6, 7), (5, 6, 3), (5, 6, 8), (5, 7, 3), (5, 7, 8), (5, 3, 8), (6, 7, 3), (6, 7, 8), (6, 3, 8), (7, 3, 8)]