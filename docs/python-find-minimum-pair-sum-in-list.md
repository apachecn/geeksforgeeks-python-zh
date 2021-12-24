# Python–在列表中查找最小对和

> 原文:[https://www . geesforgeks . org/python-find-最小对-列表中的总和/](https://www.geeksforgeeks.org/python-find-minimum-pair-sum-in-list/)

有时，我们需要找到获得最小和的对的具体问题，这可以通过在排序后获得初始的两个元素来计算。但是在某些情况下，我们不需要改变列表的顺序，在不使用额外空间的情况下在相似的列表中执行一些操作。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `min() + combination()` + lambda**
这个特殊的任务可以使用上述函数的组合来执行，其中我们使用列表理解来绑定所有功能和 min 函数来获得最小和，组合函数在内部找到所有和，lambda 函数用于计算和。

```py
# Python3 code to demonstrate
# Minimum Pair Sum 
# using list comprehension + min() + combinations() + lambda
from itertools import combinations

# initializing list
test_list = [3, 4, 1, 7, 9, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + min() + combinations() + lambda
# Minimum Pair Sum 
res = min(combinations(test_list, 2), key = lambda sub: abs(sub[0]-sub[1]))

# print result
print("The minimum sum pair is : " + str(res))
```

**Output :**

```py
The original list : [3, 4, 1, 7, 9, 1]
The minimum sum pair is : (1, 1)

```