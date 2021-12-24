# Python–在另外两个日期之间生成 k 个随机日期

> 原文:[https://www . geesforgeks . org/python-generate-k-random-date-inter-two-other-date/](https://www.geeksforgeeks.org/python-generate-k-random-dates-between-two-other-dates/)

给定两个日期，任务是编写一个 Python 程序来随机获取 K 个日期。

> **输入:** test_date1，test_date2 =日期(2015，6，3)，日期(2015，7，1)，K = 7
> 
> **输出 ：** [datetime.date（2015， 6， 18）， datetime.date（2015， 6， 25）， datetime.date（2015， 6， 29）， datetime.date（2015， 6， 11）， datetime.date（2015， 6， 11）， datetime.date（2015， 6， 10）， datetime.date（2015， 6， 24）]
> 
> **说明:**生成 2015 年 6 月 3 日至 2015 年 7 月 1 日的 7 个随机日期。
> 
> **输入:** test_date1，test_date2 =日期(2015，6，3)，日期(2015，8，1)，K = 6
> 
> **输出 ：** [datetime.date（2015， 6， 20）， datetime.date（2015， 7， 22）， datetime.date（2015， 6， 29）， datetime.date（2015， 6， 18）， datetime.date（2015， 6， 13）， datetime.date（2015， 7， 14）]
> 
> **说明:**生成 2015 年 6 月 3 日至 2015 年 8 月 1 日的 6 个随机日期。

**方法#1:使用** [**选择()**](https://www.geeksforgeeks.org/random-choices-method-in-python/) **+循环+** [**时间增量()**](https://www.geeksforgeeks.org/python-datetime-timedelta-function/)

在本例中，我们使用 1 天差的 loop 和 timedelta()提取范围内的所有日期。其中，使用选项()选择 K 个随机日期。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Random K dates in Range
# Using choices() + timedelta() + loop
from datetime import date, timedelta
from random import choices

# initializing dates ranges 
test_date1, test_date2 = date(2015, 6, 3), date(2015, 7, 1)

# printing dates 
print("The original range : " + str(test_date1) + " " + str(test_date2))

# initializing K
K = 7

res_dates = [test_date1]

# loop to get each date till end date
while test_date1 != test_date2:
    test_date1 += timedelta(days=1)
    res_dates.append(test_date1)

# random K dates from pack
res = choices(res_dates, k=K)

# printing 
print("K random dates in range : " + str(res))
```

**输出:**

> 原区间:2015-06-03 2015-07-01
> 
> K 个随机日期的范围 ： [datetime.date（2015， 6， 25）， datetime.date（2015， 6， 10）， datetime.date（2015， 6， 18）， datetime.date（2015， 6， 7）， datetime.date（2015， 6， 4）， datetime.date（2015， 6， 16）， datetime.date（2015， 6， 12）]

**方法 2:使用**[**randrange()**](https://www.geeksforgeeks.org/randrange-in-python/)**+time delta()+loop**

在这种情况下，提取范围之间的总天数，该范围用于获取元素 K 次，从使用 randrange()提取的开始日期添加随机索引号。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Random K dates in Range
# Using randrange() + timedelta() + loop
from datetime import date, timedelta
import random

# initializing dates ranges 
test_date1, test_date2 = date(2015, 6, 3), date(2015, 7, 1)

# printing dates 
print("The original range : " + str(test_date1) + " " + str(test_date2))

# initializing K
K = 7

# getting days between dates
dates_bet = test_date2 - test_date1
total_days = dates_bet.days

res = []
for idx in range(K):
    random.seed(a=None)

    # getting random days
    randay = random.randrange(total_days)

    # getting random dates 
    res.append(test_date1 + timedelta(days=randay))

# printing 
print("K random dates in range : " + str(res))
```

**输出:**

> 原区间:2015-06-03 2015-07-01
> 
> K 个随机日期的范围 ： [datetime.date（2015， 6， 26）， datetime.date（2015， 6， 5）， datetime.date（2015， 6， 6）， datetime.date（2015， 6， 18）， datetime.date（2015， 6， 21）， datetime.date（2015， 6， 15）， datetime.date（2015， 6， 12）]