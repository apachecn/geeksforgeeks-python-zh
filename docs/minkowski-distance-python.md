# Python 中的 Minkowski 距离

> 原文:[https://www.geeksforgeeks.org/minkowski-distance-python/](https://www.geeksforgeeks.org/minkowski-distance-python/)

**闵可夫斯基距离**是赋范向量空间中的度量。闵可夫斯基距离用于向量的距离相似性。给定两个或多个向量，求这些向量的距离相似度。

主要是将闵可夫斯基距离应用到机器学习中，找出距离相似度。

**示例:**

```py
Input : vector1 = 0 2 3 4
        vector2 = 2, 4, 3, 7
        p = 3

Output : distance1 = 3.5033

Input : vector1 = 1, 4, 7, 12, 23
        vector2 = 2, 5, 6, 10, 20
        p = 2

Output : distance2 = 4.0
```

**注:**此处距离 1 和距离 2 几乎相同，所以在同一近区。

## 蟒蛇 3

```py
# Python3 program to find Minkowski distance

# import math library
from math import *
from decimal import Decimal

# Function distance between two points
# and calculate distance value to given
# root value(p is root value)
def p_root(value, root):

    root_value = 1 / float(root)
    return round (Decimal(value) **
             Decimal(root_value), 3)

def minkowski_distance(x, y, p_value):

    # pass the p_root function to calculate
    # all the value of vector parallelly
    return (p_root(sum(pow(abs(a-b), p_value)
            for a, b in zip(x, y)), p_value))

# Driver Code
vector1 = [0, 2, 3, 4]
vector2 = [2, 4, 3, 7]
p = 3
print(minkowski_distance(vector1, vector2, p))
```

**输出:**

```py
3.503
```

**参考资料:**
[https://en . Wikipedia . org/wiki/Minkowski _ distance](https://en.wikipedia.org/wiki/Minkowski_distance)