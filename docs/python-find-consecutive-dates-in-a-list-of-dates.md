# Python–在日期列表中查找连续的日期

> 原文:[https://www . geesforgeks . org/python-在日期列表中查找连续日期/](https://www.geeksforgeeks.org/python-find-consecutive-dates-in-a-list-of-dates/)

给定一个日期列表，任务是编写一个 Python 程序来检查列表中的所有日期是否连续。

> **输入 ：** [日期时间（2019， 12， 30）， 日期时间（2019， 12， 31）， 日期时间（2020， 1， 1）， 日期时间（2020， 1， 2）， 日期时间（2020， 1， 3）， 日期时间（2020， 1， 4）]
> 
> **输出:**真
> 
> **说明:**所有日期均为连续，从 2019 年 12 月 30 日至 2020 年 1 月 4 日。
> 
> **输入 ：** [日期时间（2019， 12， 29）， 日期时间（2019， 12， 31）， 日期时间（2020， 1， 1）， 日期时间（2020， 1， 2）， 日期时间（2020， 1， 3）， 日期时间（2020， 1， 4）]
> 
> **输出:**假
> 
> **说明:**非连续日期。

**方法#1:使用天()+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在本例中，我们通过使用天数()检查与前一个日期的天数差异来检查连续日期。所有日期的迭代都是使用循环完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test if dates are consecutive
# Using days() + loop
from datetime import datetime, timedelta

# initializing list
test_list = [datetime(2019, 12, 30), datetime(2019, 12, 31), 
             datetime(2020, 1, 1), datetime(2020, 1, 2),
             datetime(2020, 1, 3), datetime(2020, 1, 4)]

# printing original list
print("The original list is : " + str(test_list))

# using loop for iterating all elements
res = True
for idx in range(1, len(test_list)):

    # checking for 1 day time difference
    if (test_list[idx] - test_list[idx - 1]).days != 1:
        res = False
        break

# printing result
print("Are dates consecutive : " + str(res))
```

**输出:**

> 原始列表是：[datetime.datetime（2019， 12， 30， 0， 0）， datetime.datetime（2019， 12， 31， 0， 0）， datetime.datetime（2020， 1， 1， 0， 0）， datetime.datetime（2020， 1， 2， 0， 0）， datetime.datetime（2020， 1， 3， 0， 0）， datetime.datetime（2020， 1， 4， 0， 0）]
> 
> 日期是否连续:真

**方法 2:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+days()**

与上述方法类似，这里唯一的区别是 all()用于检查每天的连续情况，以获得更紧凑的解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test if dates are consecutive
# Using all() + days()
from datetime import datetime, timedelta

# initializing list
test_list = [datetime(2019, 12, 30), datetime(2019, 12, 31), 
             datetime(2020, 1, 1), datetime(2020, 1, 2),
             datetime(2020, 1, 3), datetime(2020, 1, 4)]

# printing original list
print("The original list is : " + str(test_list))

# using loop for iterating all elements
res = all((test_list[idx] - test_list[idx - 1]).days ==
          1 for idx in range(1, len(test_list)))

# printing result
print("Are dates consecutive : " + str(res))
```

**输出:**

> 原始列表是：[datetime.datetime（2019， 12， 30， 0， 0）， datetime.datetime（2019， 12， 31， 0， 0）， datetime.datetime（2020， 1， 1， 0， 0）， datetime.datetime（2020， 1， 2， 0， 0）， datetime.datetime（2020， 1， 3， 0， 0）， datetime.datetime（2020， 1， 4， 0， 0）]
> 
> 日期是否连续:真