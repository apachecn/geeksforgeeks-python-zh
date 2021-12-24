# Python–查找所有嵌套列表的起始索引

> 原文:[https://www . geesforgeks . org/python-find-start-index-of-all-nested-list/](https://www.geeksforgeeks.org/python-find-starting-index-of-all-nested-lists/)

在本文中，给定一个矩阵，任务是编写一个 Python 程序来计算所有嵌套列表的起始索引。

**示例:**

> **输入:** test_list = [[5]，[9，3，1，4]，[3，2]，[4，7，8，3，1，2]，[3，4，5]]
> 
> **输出:**【0，1，5，7，13】
> 
> **说明:**1+4 = 2 个初始列表的长度= 5，3，第 3 个列表从第 5 个索引[基于 0 的索引]开始，
> 
> 因此是 5。作为结果列表中的第三个元素。
> 
> **输入:** test_list = [[5]，[9，3，1，4]，[3，2]，[3，4，5]]
> 
> **输出:**【0，1，5，7】
> 
> **说明:**1+4 = 2 个初始列表的长度= 5，3，第 3 个列表从第 5 个索引[基于 0 的索引]开始，
> 
> 因此是 5。作为结果列表中的第三个元素。

**方法#1:使用 loop +** [**len()**](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，使用 len()计算每个子列表的长度，并对其求和、累加，然后作为中间结果相加。初始索引是子列表长度的导数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Initial element index in Matrix
# Using loop

# initializing list
test_list = [[5], [9, 3, 1, 4], [3, 2], [4, 7, 8, 3, 1, 2], [3, 4, 5]]

# printing original list
print("The original list is : " + str(test_list))

res = []
lens = 0
for sub in test_list:

    # lengths of sublist computed
    res.append(lens)
    lens += len(sub)

# printing result
print("Initial element indices : " + str(res))
```

**输出:**

> 原来的名单是:[[5]，[9，3，1，4]，[3，2]，[4，7，8，3，1，2]，[3，4，5]]
> 
> 初始元素索引:[0，1，5，7，13]

**方法 2:使用** [**累加()**](https://www.geeksforgeeks.org/python-itertools-accumulate/) **+** [**地图()**](https://www.geeksforgeeks.org/python-map-function/) **+ len()**

在本例中，我们使用累加()执行求和任务，map()用于获取使用 len()计算的所有子列表的长度。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Initial element index in Matrix
# Using accumulate() + map() + len()
from itertools import accumulate

# initializing list
test_list = [[5], [9, 3, 1, 4], [3, 2], [4, 7, 8, 3, 1, 2], [3, 4, 5]]

# printing original list
print("The original list is : " + str(test_list))

# ignoring last index using "-1"
# sum starting at 0
res = [0, *accumulate(map(len, test_list[:-1]))]

# printing result
print("Initial element indices : " + str(res))
```

**输出:**

> 原来的名单是:[[5]，[9，3，1，4]，[3，2]，[4，7，8，3，1，2]，[3，4，5]]
> 
> 初始元素索引:[0，1，5，7，13]

**方法#3:使用类型()和循环以及一个 if 语句**

在这种情况下，我们只需检查列表中元素的类型，如果它是另一个列表，则打印它的索引，否则不打印。无论列表中非列表类型元素的数量是多少，此方法都将有效

## 蟒蛇 3

```py
# This will print all the starting indexes
# of sublists inside this list
lis = [[1,2,3],4,5,[6,7,8],9,0,[10]]

for i in lis:
    if type(i) == list:
        print(lis.index(i), end=",")

# This code is contributed by BABAji
```

**输出:**

```py
0,3,6,
```