# Python–K 范围内的组日期

> 原文:[https://www . geesforgeks . org/python-group-date-in-k-ranges/](https://www.geeksforgeeks.org/python-group-dates-in-k-ranges/)

给定一个日期列表，将从列表的初始日期开始的连续一天中的日期分组。我们将从最小的日期开始，形成一组 K 个日期的每个连续范围。

> **输入 ：** test_list = [日期时间（2020， 1， 4）， 日期时间（2019， 12， 30）， 日期时间（2020， 1， 7）， 日期时间（2019， 12， 27）， 日期时间（2020， 1， 20）， 日期时间（2020， 1， 10）]， K = 10
> 
> **输出 ：** [（0， [datetime.datetime（2019， 12， 27， 0， 0）， datetime.datetime（2019， 12， 30， 0， 0）， datetime.datetime（2020， 1， 4， 0， 0）]）， （1， [datetime.datetime（2020， 1， 7， 0， 0）， datetime.datetime（2020， 1， 10， 0， 0）]）， （2， [datetime.datetime（2020， 1， 20， 0， 0）]）
> 
> **说明:**12 月 27 日-1 月 4 日与 diff 同组。如果日期少于 10 天，成功地，每组日期按 10 天增量分组。
> 
> **输入 ：** test_list = [日期时间（2020， 1， 4）， 日期时间（2019， 12， 30）， 日期时间（2020， 1， 7）， 日期时间（2019， 12， 27）， 日期时间（2020， 1， 20）， 日期时间（2020， 1， 10）]， K = 14
> 
> **输出 ：** [（0， [datetime.datetime（2019， 12， 27， 0， 0）， datetime.datetime（2019， 12， 30， 0， 0）， datetime.datetime（2020， 1， 4， 0， 0）， datetime.datetime（2020， 1， 7， 0， 0）]）， （1， [datetime.datetime（2020， 1， 10， 0， 0）， datetime.datetime（2020， 1， 20， 0，0）]）]
> 
> **说明:**12 月 27 日-1 月 7 日与 diff 同组。成功地，每一组日期按 14 天增量分组。

**方法:使用**[**group by()**](https://www.geeksforgeeks.org/itertools-groupby-in-python/)**+sort()**

在这种情况下，我们对日期进行排序，然后根据分组功能对一组日期进行分组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Group dates in K ranges
# Using groupby() + sort()
from itertools import groupby
from datetime import datetime

# initializing list
test_list = [datetime(2020, 1, 4),
             datetime(2019, 12, 30), 
             datetime(2020, 1, 7),
             datetime(2019, 12, 27),
             datetime(2020, 1, 20), 
             datetime(2020, 1, 10)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 7

# initializing start date 
min_date = min(test_list)

# utility fnc to form groupings
def group_util(date):
    return (date-min_date).days // K

# sorting before grouping
test_list.sort()

temp = []
# grouping by utility function to group by K days
for key, val in groupby(test_list , key = lambda date : group_util(date)):
    temp.append((key, list(val)))

# using strftime to convert to userfriendly
# format
res = []
for sub in temp:
  intr = []
  for ele in sub[1]:
    intr.append(ele.strftime("%Y/%m/%d"))
  res.append((sub[0], intr))

# printing result
print("Grouped Digits : " + str(res))
```

**输出:**

> 原始列表是：[datetime.datetime（2020， 1， 4， 0， 0）， datetime.datetime（2019， 12， 30， 0， 0）， datetime.datetime（2020， 1， 7， 0， 0）， datetime.datetime（2019， 12， 27， 0， 0）， datetime.datetime（2020， 1， 20， 0， 0）， datetime.datetime（2020， 1， 10， 0， 0）]
> 
> 分组数字:[(0，['2019/12/27 '，' 2019/12/30'])，(1，['2020/01/04 '，' 2020/01/07'])，(2，['2020/01/10']，(3，['2020/01/20'])