# 给定两个数组，求 n+m-1 个唯一和对

> 原文:[https://www . geesforgeks . org/given-two-array-find-nm-1-unique-sum-pairs/](https://www.geeksforgeeks.org/given-two-arrays-find-nm-1-unique-sum-pairs/)

分别给定大小为 N 和 M 的 2 个整数数组 A 和 B(每个数组中没有重复的元素)，形成 N+M–1 对，每对数组中有一个元素，这样所有对的和是唯一的。对于每一对，打印它们各自数组中元素的索引。

**示例:**

```
Input: N = 5, M = 3
       A = [6, 5, 7, 1, 3]
       B = [2, 4, 8]

Output: 2 0
        2 1
        2 2
        3 0
        4 0
        1 0
        0 0

We have to form 5 + 3 - 1 = 7 pairs. These pairs are:
(7, 2), (7, 4), (7, 8), (1, 2), (3, 2), (5, 2), (6, 2)
All have unique sum

```

**蛮力方法:**我们可以在 A 和 B 两个数组上运行一个循环，找到前 N+M-1 个唯一的和对，并沿途打印它们的索引。
为了检查某个特定的金额是否已经被使用，我们制作了一个 python bool 字典。如果该和的字典值为假，则意味着它是一个新的和值。如果为真，则该总和已被使用。

**代码:**

```
from collections import defaultdict as dd

# Function to form unique sum pairs
def unique_pairs():

    # Python Bool Dictionary
    d = dd(bool)
    ct = 0

    # For every element of A, Find
    # a unique sum pair in B. Break
    # the loop after N + M-1 pairs
    for i in range(n):
        for j in range(m):
            if(ct == n + m-1):
                break
            sm = a[i] + b[j]
            if(d[sm] == False):
                d[sm] = True
                ct+= 1
                print(i, j)

n, m = 6, 4
a = [ 6, 4, 3, 5, 8, 2 ]
b = [ 3, 5, 4, 2 ]

unique_pairs()
```

**输出:**

```
0 0
0 1
0 2
0 3
1 0
1 3
2 3
4 1
4 2

```

**时间复杂度:**由于我们使用嵌套循环遍历数组，时间复杂度变成了 O( ![n^2](img/bc310b612b5fbf7a1964db0ae906a889.png "Rendered by QuickLaTeX.com"))。

**高效方法:**一旦我们对两个数组进行了排序，首先我们可以通过将数组 A 的所有元素与数组 B 的第一个元素配对，然后将数组 B 的其他 M–1 个元素与数组 A 的最后一个元素配对，从而形成 N 个唯一的和对

**代码:**

```
from collections import defaultdict as dd

# Function to form unique sum pairs
def unique_pairs_sort():

    # Python Int Dictionary
    da = dd(int)
    db = dd(int)

    # Make a dictionary to store index
    for i in range(n):
        da[a[i]] = i
    for i in range(m):
        db[b[i]] = i

    # Sorting the arrays
    a.sort(); b.sort()

    # N pairs of A with B[0]
    for i in range(n):
        print(da[a[i]], db[b[0]])

    # M-1 pairs of B with A[N-1]
    for i in range(1, m):
        print(da[a[-1]], db[b[i]])

n, m = 6, 4
a = [ 6, 4, 3, 5, 8, 2 ]
b = [ 3, 5, 4, 2 ]

unique_pairs_sort()
```

**输出:**

```
5 3
2 3
1 3
3 3
0 3
4 3
4 0
4 2
4 1

```

**时间复杂度:**这个的复杂度等于排序所需的时间:O(n Log n)。
**空间复杂度:**因为我们使用了两个不同的地图/字典来存储数组的索引。时间复杂度为 O(n + m)，其中 n 是第一个数组的大小，m 是第二个数组的大小。