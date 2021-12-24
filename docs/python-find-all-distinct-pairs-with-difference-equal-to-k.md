# Python |查找差异等于 k 的所有不同对

> 原文:[https://www . geesforgeks . org/python-find-all-distinct-pairs-with-different-equal-to-k/](https://www.geeksforgeeks.org/python-find-all-distinct-pairs-with-difference-equal-to-k/)

给定一个整数列表和一个正整数 *k* ，编写一个 Python 程序来计算所有差异等于 k 的不同对。

**示例:**

```
Input : [1, 5, 3, 4, 2], k = 3
Output : [(5, 2), (4, 1)]

Input : [8, 12, 16, 4, 0, 20], k = 4
Output : [(8, 4), (12, 8), (16, 12), (4, 0), (20, 16)]

```

**方法#1 :** Python 列表理解

我们将使用列表理解，使用“e1”和“e2”这两个循环遍历给定的列表。我们检查 *e1-e2 == k* 是否存在，并分别返回(e1，e2)元组。最后，将返回一个包含所需元组的列表。

```
# Python3 program to Find all distinct 
# pairs with difference equal to k

def findPairs(lst, k):

    return [(e1, e2) for e1 in lst 
            for e2 in lst if (e1-e2 == k)]

# Driver code
lst = [1, 5, 3, 4, 2]
k = 3
print(findPairs(lst, k))
```

**Output:**

```
[(5, 2), (4, 1)]

```

**进场#2 :**

相对于上述方法，这是一种有效的方法，因为它只使用 O(n)空间。我们取一个空列表来存储输出。然后，我们使用带有迭代器“e”的循环遍历给定的列表。在每次迭代中，我们检查的是 *e+k* ，即 *e* 所需的配对整数是否可用。如果是，我们将元组追加到“res”中。

```
# Python3 program to Find all distinct 
# pairs with difference equal to k

def findPairs(lst, k):
    res = []
    for e in lst:
        if e + k in lst:
            res.append(tuple((e, e + k)))

    return res

# Driver code
lst = [1, 5, 3, 4, 2]
k = 3
print(findPairs(lst, k))
```

**Output:**

```
[(1, 4), (2, 5)]

```

**从`itertools`模块接近#3 :** `combinations()`

最好的方法是使用来自 *itertools* 模块的内置函数。*组合()*对输入中 n 个元素的所有组合的元组产生迭代器。我们利用这些组合，输出那些有“k”差的组合。

```
# Python3 program to Find all distinct 
# pairs with difference equal to k
from itertools import combinations

def findPairs(lst, k):
    return [(x, y) for x, y in combinations(lst, r = 2)
                   if abs(x - y) == k]

# Driver code
lst = [1, 5, 3, 4, 2]
k = 3
print(findPairs(lst, k))
```

**Output:**

```
[(1, 4), (5, 2)]

```