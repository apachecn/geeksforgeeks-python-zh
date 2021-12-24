# Python 中的二分搜索法(等分)

> 原文:[https://www . geesforgeks . org/binary-search-平分-in-python/](https://www.geeksforgeeks.org/binary-search-bisect-in-python/)

[二分搜索法](https://www.geeksforgeeks.org/binary-search/)是一种用于在排序列表中搜索元素的技术。在本文中，我们将研究库函数来做二分搜索法。

**寻找元素的第一次出现。**

> 平分。平分 _ 左(a，x，lo=0，hi=len(a)):返回排序列表中 x 最左边的插入点。最后两个参数是可选的，它们用于在子列表中搜索。

```py
# Python code to demonstrate working
# of binary search in library
from bisect import bisect_left

def BinarySearch(a, x):
    i = bisect_left(a, x)
    if i != len(a) and a[i] == x:
        return i
    else:
        return -1

a  = [1, 2, 4, 4, 8]
x = int(4)
res = BinarySearch(a, x)
if res == -1:
    print(x, "is absent")
else:
    print("First occurrence of", x, "is present at", res)
```

**Output:**

```py
First occurrence of 4 is present at 2

```

**寻找小于 x 的最大值**

```py
# Python code to demonstrate working
# of binary search in library
from bisect import bisect_left

def BinarySearch(a, x):
    i = bisect_left(a, x)
    if i:
        return (i-1)
    else:
        return -1

# Driver code
a  = [1, 2, 4, 4, 8]
x = int(7)
res = BinarySearch(a, x)
if res == -1:
    print("No value smaller than ", x)
else:
    print("Largest value smaller than ", x, " is at index ", res)
```

**Output:**

```py
Largest value smaller than  7  is at index  3

```

**寻找最右边的出现**

> 平分。平分 _ 右(a，x，lo=0，hi=len(a))返回排序列表 a 中 x 最右边的插入点。最后两个参数是可选的，它们用于在子列表中搜索。

```py
# Python code to demonstrate working
# of binary search in library
from bisect import bisect_right

def BinarySearch(a, x):
    i = bisect_right(a, x)
    if i != len(a)+1 and a[i-1] == x:
        return (i-1)
    else:
        return -1

a  = [1, 2, 4, 4]
x = int(4)
res = BinarySearch(a, x)
if res == -1:
    print(x, "is absent")
else:
    print("Last occurrence of", x, "is present at", res)
```

**Output:**

```py
Last occurrence of 4 is present at 3

```

请参考[二分搜索法](https://www.geeksforgeeks.org/binary-search/)来编写自己的二分搜索法代码。

**参考:**T2[https://docs.python.org/3/library/bisect.html](https://docs.python.org/3/library/bisect.html)