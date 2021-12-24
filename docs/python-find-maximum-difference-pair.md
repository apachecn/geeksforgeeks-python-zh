# Python |查找最大差异对

> 原文:[https://www . geesforgeks . org/python-find-最大差异-pair/](https://www.geeksforgeeks.org/python-find-maximum-difference-pair/)

有时，我们需要找到获得产生最大差异的对的具体问题，这可以通过排序并获得列表的第一个和最后一个元素来解决。但是在某些情况下，我们不需要改变列表的顺序，在不使用额外空间的情况下，在类似的列表中执行一些操作。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+`max()`+`combination()`+λ**

这个特殊的任务可以使用上述函数的组合来执行，其中我们使用列表理解来绑定所有功能，使用 max 函数来获得最大差异，组合函数在内部找到所有差异，使用 lambda 函数来计算差异。

```
# Python3 code to demonstrate
# maximum difference pair
# using list comprehension + max() + combinations() + lambda
from itertools import combinations

# initializing list
test_list = [3, 4, 1, 7, 9, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + max() + combinations() + lambda
# maximum difference pair
res = max(combinations(test_list, 2), key = lambda sub: abs(sub[0]-sub[1]))

# print result
print("The maximum difference pair is : " + str(res))
```

**Output :**

```
The original list : [3, 4, 1, 7, 9, 1]
The maximum difference pair is : (1, 9)

```

**方法二:使用列表理解+`nlargest()`+`combination()`+λ**

如果需要，这种方法不仅有可能找到单个最大值，而且有可能找到 k 个最大差值对，并使用 n 目标函数而不是 max 函数来实现这一功能。

```
# Python3 code to demonstrate
# maximum difference pair
# using list comprehension + nlargest() + combinations() + lambda
from itertools import combinations
from heapq import nlargest

# initializing list
test_list = [3, 4, 1, 7, 9, 8]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + max() + combinations() + lambda
# maximum difference pair
# computes 2 maximum pair differences
res = nlargest(2, combinations(test_list, 2), 
         key = lambda sub: abs(sub[0]-sub[1]))

# print result
print("The maximum difference pair is : " + str(res))
```

**Output :**

```
The original list : [3, 4, 1, 7, 9, 8]
The maximum difference pair is : [(1, 9), (1, 8)]

```