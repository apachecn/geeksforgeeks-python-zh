# Python–元素的分组连续范围索引

> 原文:[https://www . geeksforgeeks . org/python-分组-连续-范围-元素索引/](https://www.geeksforgeeks.org/python-grouped-consecutive-range-indices-of-elements/)

给定元素列表，对于元组列表，其中每个代表每个元素出现的连续性。

> **输入** : test_list = [1，1，5，6，5，5]
> **输出** : {1: [(0，1)]，5: [(2，2)，(4，5)]，6: [(3，3)]}
> **解释** : 5 出现在第二个 idx，也在第四个和第五个索引中延续，因此记录范围。
> 
> **输入** : test_list = [5，5，5，5，5，5]
> **输出** : {5: [(0，5)]}
> **解释**:只出现 5 个，遂记录。

**方法:使用 group by()+default dict()+len()+loop**

在这种情况下，我们使用 groupby()执行连续元素分组，defaultdict()用于初始化元组列表，len()用于获取重复长度。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Grouped Consecutive Range Indices of Elements
# Using groupby() + defaultdict() + len() + loop
from itertools import groupby
from collections import defaultdict

# initializing lists
test_list = [1, 1, 5, 6, 5, 5, 6, 6, 6, 1, 5, 5]

# printing string
print("The original list : " + str(test_list))

idx = 0
res = defaultdict(list)

# grouping Consecutives
for key, sub in groupby(test_list):
    ele = len(list(sub))

    # append strt index, and till index
    res[key].append((idx, idx + ele - 1))
    idx += ele

# printing results 
print("The grouped dictionary : " + str(dict(res)))
```

**Output**

```
The original list : [1, 1, 5, 6, 5, 5, 6, 6, 6, 1, 5, 5]
The grouped dictionary : {1: [(0, 1), (9, 9)], 5: [(2, 2), (4, 5), (10, 11)], 6: [(3, 3), (6, 8)]}

```