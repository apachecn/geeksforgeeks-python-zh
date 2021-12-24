# Python–每第 Kth 个片段交叉连接

> 原文:[https://www . geesforgeks . org/python-交叉连接-每 kth-segment/](https://www.geeksforgeeks.org/python-cross-join-every-kth-segment/)

给定两个列表，在每个 Kth 位置提取替换元素。

> **输入** : test_list1 = [4，3，8，2，6，7]，test_list2 = [5，6，7，4，3，1]，K = 3
> **输出** : [4，3，8，5，6，7，2，6，7，4，3，1]
> **解释** : 4，3，8 之后从其他列表中提取 5，6，以此类推。
> **输入** : test_list1 = [4，3，8，2]，test_list2 = [5，6，7，4]，K = 2
> **输出** : [4，3，5，6，8，2，7，4]
> **解释** : 4，3 之后从其他列表中提取 5，6，以此类推。

**方法#1:使用发电机【产量】+回路**

在这种情况下，我们对所有元素进行迭代，嵌套以在每次传递时从两个列表中获得 K 个元素。产量用于在处理数据段时动态返回数据段。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Cross Join every Kth segment
# Using yield + loop

# helper function
def pair_merge(test_list1, test_list2, K):
    idx1 = 0
    idx2 = 0
    while(idx1 < len(test_list1)):

        # get K segments
        for i in range(K):
            yield test_list1[idx1]
            idx1 += 1
        for i in range(K):
            yield test_list2[idx2]
            idx2 += 1

# initializing lists
test_list1 = [4, 3, 8, 2, 6, 7]
test_list2 = [5, 6, 7, 4, 3, 1]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 2

# calling helper func. in generator expression
res = [ele for ele in pair_merge(test_list1, test_list2, K)]

# printing result
print("The cross joined list : " + str(res))
```

**Output**

```
The original list 1 is : [4, 3, 8, 2, 6, 7]
The original list 2 is : [5, 6, 7, 4, 3, 1]
The cross joined list : [4, 3, 5, 6, 8, 2, 7, 4, 6, 7, 3, 1]
```

**方法二:使用 zip _ longest 列表理解**

在这种情况下，我们使用 zip _ longest 获取每个列表的所有元素，列表理解用于两个列表中的迭代任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Cross Join every Kth segment
# Using zip_longest() + list comprehension
from itertools import zip_longest, chain

# initializing lists
test_list1 = [4, 3, 8, 2, 6, 7]
test_list2 = [5, 6, 7, 4, 3, 1]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 2

# zip_longest to get segments
res = [y for idx in zip(zip_longest(*[iter(test_list1)] * K),
      zip_longest(*[iter(test_list2)] * K)) for y in chain.from_iterable(idx) if y]

# printing result
print("The cross joined list : " + str(res))
```

**Output**

```
The original list 1 is : [4, 3, 8, 2, 6, 7]
The original list 2 is : [5, 6, 7, 4, 3, 1]
The cross joined list : [4, 3, 5, 6, 8, 2, 7, 4, 6, 7, 3, 1]
```