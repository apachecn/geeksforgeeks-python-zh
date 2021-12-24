# 查找一年中每天发生的次数

> 原文:[https://www . geesforgeks . org/find-一年中每天发生的次数/](https://www.geeksforgeeks.org/find-number-of-times-every-day-occurs-in-a-year/)

给一年时间。你的任务是找出一年中每天的数字，即该年中周一、周二、周三、周四、周五、周六、周日的数字。
**例:**

```
Input: 2019
Output: Monday-52
        Tuesday-53
        Wednesday-52
        Thursday-52
        Friday-52
        Saturday-52
        Sunday-52

Input: 2024
Output: Monday-53
        Tuesday-53
        Wednesday-52
        Thursday-52
        Friday-52
        Saturday-52
        Sunday-52
```

**观察:**我们要做一些关键的观察。第一个是一年中至少有 52 周，所以一年中每天至少发生 52 次。由于 52*7 等于 364，因此任何一年的 1 月 1 日这一天将出现 53 次，如果这一年是闰年，那么 1 月 2 日这一天也将出现 53 次。
**方法:**创建一个列表，大小为 7，初始值为 52，最小出现次数为 52。找到第一天的索引。计算发生的天数为 53 天。
下面是实现。

## 蟒蛇 3

```
# python program Find number of
# times every day occurs in a Year

import datetime
import calendar

def day_occur_time(year):

    # stores days in a week
    days = [ "Monday", "Tuesday", "Wednesday", 
           "Thursday",  "Friday", "Saturday",
           "Sunday" ]

    # Initialize all counts as 52
    L = [52 for i in range(7)]

    # Find the index of the first day
    # of the year
    pos = -1
    day = datetime.datetime(year, month = 1, day = 1).strftime("%A")
    for i in range(7):
        if day == days[i]:
            pos = i

    # mark the occurrence to be 53 of 1st day
    # and 2nd day if the year is leap year
    if calendar.isleap(year):
        L[pos] += 1
        L[(pos+1)%7] += 1

    else:
        L[pos] += 1

    # Print the days
    for i in range(7):
        print(days[i], L[i])

# Driver Code
year = 2019
day_occur_time(year)
```

**输出:**

```
Monday 52
Tuesday 52
Wednesday 52
Thursday 52
Friday 53
Saturday 53
Sunday 52
```