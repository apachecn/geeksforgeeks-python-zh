# Python–列表中元素的分数频率

> 原文:[https://www . geesforgeks . org/python-列表中元素的分数频率/](https://www.geeksforgeeks.org/python-fractional-frequency-of-elements-in-list/)

给定一个列表，得到每个元素在每个位置的分数频率。

> **输入** : test_list = [4，5，4，6，7，5，4，5，4]
> **输出** : ['1/4 '，' 1/3 '，' 2/4 '，' 1/1 '，' 1/1 '，' 2/3 '，' 3/4 '，' 3/3 '，' 4/4']
> **解释**:直到第 1 个索引，4 出现总出现次数的 1/4，以此类推。
> **输入** : test_list = [4，5，4，6，7，5]
> **输出** : ['1/2 '，' 1/2 '，' 2/2 '，' 1/1 '，' 1/1 '，' 2/2']
> **解释** : 4 出现在总出现次数的 1/2 直到第 1 次索引，以此类推。

**方法:使用 Counter() + loop +字典理解**

在本文中，我们使用 Counter()来获取列表中每个元素的频率，并形成分数的分母部分。每个元素的分子都初始化为 0。然后使用循环将 numberator 中的元素相加，并在分母中加入总频率。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Fractional Frequency of elements in List
# Using Counter() + loop + dictionary comprehension
from collections import Counter

# initializing list
test_list = [4, 5, 4, 6, 7, 5, 4, 5, 4, 6, 4, 6]

# printing original list
print("The original list is : " + str(test_list))

# initializing numerator
number = {idx : 0 for idx in set(test_list)}

# initializing denominator
denom = Counter(test_list)

res = []
for ele in test_list:

    # increasing counter
    number[ele] += 1
    res.append(str(number[ele]) + '/' + str(denom[ele]))

# printing result
print("Fractional Frequency List : " + str(res))
```

**Output**

```
The original list is : [4, 5, 4, 6, 7, 5, 4, 5, 4, 6, 4, 6]
Fractional Frequency List : ['1/5', '1/3', '2/5', '1/3', '1/1', '2/3', '3/5', '3/3', '4/5', '2/3', '5/5', '3/3']
```