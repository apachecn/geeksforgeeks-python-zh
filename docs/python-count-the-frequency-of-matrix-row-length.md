# Python–统计矩阵行长度的频率

> 原文:[https://www . geeksforgeeks . org/python-计算矩阵行长的频率/](https://www.geeksforgeeks.org/python-count-the-frequency-of-matrix-row-length/)

给定一个矩阵，任务是编写一个 Python 程序来获得其行长度的计数频率。

> **输入:** test_list = [[6，3，1]，[8，9]，[2]，[10，12，7]，[4，11]]
> 
> **输出:** {3: 2，2: 2，1: 1}
> 
> **说明:**存在 2 个长度为 3 的列表，2 个大小为 2 的列表和 1 个长度为 1 的列表。
> 
> **输入:** test_list = [[6，3，1]，[8，9]，[10，12，7]，[4，11]]
> 
> **输出:** {3: 2，2: 2}
> 
> **说明:**存在 2 个长度为 3 的列表，2 个大小为 2 的列表。

**方法一:使用** [**字典**](https://www.geeksforgeeks.org/python-dictionary/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们检查每一行的长度，如果长度已经出现在记忆字典中，那么结果将增加，或者如果出现新的大小，元素将被注册为新的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Row lengths counts
# Using dictionary + loop

# initializing list
test_list = [[6, 3, 1], [8, 9], [2], 
             [10, 12, 7], [4, 11]]

# printing original list
print("The original list is : " + str(test_list))

res = dict()
for sub in test_list:

    # initializing incase of new length
    if len(sub) not in res:
        res[len(sub)] = 1

    # increment in case of length present
    else:
        res[len(sub)] += 1

# printing result
print("Row length frequencies : " + str(res))
```

**输出:**

```py
The original list is : [[6, 3, 1], [8, 9], [2], [10, 12, 7], [4, 11]]
Row length frequencies : {3: 2, 2: 2, 1: 1}
```

**方法 2:使用** [**计数器()**](https://www.geeksforgeeks.org/counters-in-python-set-1/) **+** [**地图()**](https://www.geeksforgeeks.org/python-map-function/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，map()和 len()获得矩阵中每个子列表的长度，Counter 用于保持每个长度的频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Row lengths counts
# Using Counter() + map() + len()
from collections import Counter

# initializing list
test_list = [[6, 3, 1], [8, 9], [2],
             [10, 12, 7], [4, 11]]

# printing original list
print("The original list is : " + str(test_list))

# Counter gets the frequencies of counts
# map and len gets lengths of sublist
res = dict(Counter(map(len, test_list)))

# printing result
print("Row length frequencies : " + str(res))
```

**输出:**

```py
The original list is : [[6, 3, 1], [8, 9], [2], [10, 12, 7], [4, 11]]
Row length frequencies : {3: 2, 2: 2, 1: 1}
```