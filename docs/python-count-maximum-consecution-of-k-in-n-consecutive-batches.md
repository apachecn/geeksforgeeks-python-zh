# Python–计算连续 N 个批次中 K 的最大连续数

> 原文:[https://www . geeksforgeeks . org/python-count-maximum-continuation-of-k-in-on-continuous-battery/](https://www.geeksforgeeks.org/python-count-maximum-consecution-of-k-in-n-consecutive-batches/)

给定一个列表，任务是编写一个 Python 程序来计算在每批大小为 n 的数据中，K 连续出现的最大次数

**示例:**

> **输入:** test_list = [4，4，5，4，4，1，2，3，4，4，4，4，4，4，5，6，7，4，4，5，3，4，4，7，4，4，4，4，4，4，4，4，4，4，5，6，3，5，4，4，4，4，1，4，2，4，4，4]，N = 15，K = 4
> 
> **输出:**【6，3，3】
> 
> **说明:**第一批 15 个元素中，4 个出现在连续、2、3、6。时代周刊。因为 6 是最大值，所以是输出之一。
> 
> **输入:** test_list = [4、4、5、4、4、4、1、2、3、4、4、4、4、4、4、5、6、7、4、4、5、3、4、4、4、7、4、4、4、4、4、4、4、4、4]，N = 15，K = 4
> 
> **输出:**【6，3】
> 
> **说明:**第一批 15 个元素中，4 个出现在连续、2、3、6。时代周刊。因为 6 是最大值，所以是输出之一。

**方法:使用**[**group by()**](https://www.geeksforgeeks.org/itertools-groupby-in-python/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+切片**

在这种情况下，我们使用切片和使用范围来跳转 K 个元素来开始为每个批次分组来获得每个连续。max()获取每批中 K 个连续组的最大长度。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum consecution of K in N consecutive batches
# Using groupby() + max() + list comprehension + slicing
from itertools import groupby

# initializing list
test_list = [4, 4, 5, 4, 4, 4, 1, 2, 3, 4, 4, 4, 4, 4, 4,
             4, 5, 6, 7, 4, 4, 5, 3, 4, 4, 4, 7, 4, 4, 4,
             5, 6, 3, 5, 4, 4, 4, 6, 4, 4, 1, 4, 2, 4, 4]

# printing original list
print("The original list is : " + str(test_list))

# initializing N
N = 15

# initializing K
K = 4

# max() getting max. consecution of K, ranges being evaluated using slices
# and skips using range()
res = [max(len(list(group)) for ele, group in groupby(sub) if ele == K)
          for sub in (test_list[idx : idx + N]
          for idx in range(0, len(test_list), N))]

# printing result
print("Maximum consecution of K for each batch : " + str(res))
```

**输出:**

> 原来的名单是:[4，4，5，4，4，4，1，2，3，4，4，4，4，4，4，4，5，6，7，4，4，5，3，4，4，4，7，4，4，4，5，6，3，5，5，4，4，6，4，4，4，4，4，4，1，4，2，4，4]
> 
> 每批最大连续数为[6，3，3]