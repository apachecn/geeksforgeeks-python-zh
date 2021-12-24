# Python–不同的正整数和到 K

> 原文:[https://www . geesforgeks . org/python-distinct-正整数-sum-to-k/](https://www.geeksforgeeks.org/python-distinct-positive-integers-sum-to-k/)

给定一个和 K，然后提取不同的正数达到和。

> **输入** : K = 17
> **输出**:【1，2，3，4，7】
> **说明**:列表求和等于 17。
> 
> **输入** : K = 21
> **输出**:【1，2，3，4，11】
> **解释**:列表求和等于 21。

**方法#1:使用循环**

在这种情况下，我们取能达到 K 的最小可能值，对于最后一个值，我们从 K 减去直到该点的求和值的剩余值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Distinct Positive Integers Sum to K
# Using loop

# initializing K
K = 19

# printing K
print("The value of K : " + str(K))

res = []
idx = 0
for ele in range(1, K):
    idx += ele

    # checking for last element point 
    if K - idx < ele + 1:

        # appending initial elements
        res.extend(list(range(1, ele)))

        # appending last element left
        res.append(K - idx + ele)
        break

# printing result 
print("The Required elements : " + str(res))
```

**Output**

```
The value of K : 19
The Required elements : [1, 2, 3, 4, 9]

```

**方法 2:使用组合()+求和()**

在这种情况下，我们使用组合()获得元素，并使用求和来检查求和，这不会以贪婪但随机的方式获得所需的求和。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Distinct Positive Integers Sum to K
# Using combinations() + sum()
from itertools import combinations

# initializing K
K = 19

# printing K
print("The value of K : " + str(K))

res = []
flag = 0
for idx in range(K - 1, 0, -1):

    # forming combinations
    for sub in combinations(range(1, K), idx):
        if sum(sub) == K and flag == 0:
            res.extend(list(sub))
            flag = 1
            break
        else:
            continue
        break

# printing result
print("The Required elements : " + str(res))
```

**Output**

```
The value of K : 19
The Required elements : [1, 2, 3, 4, 9]

```