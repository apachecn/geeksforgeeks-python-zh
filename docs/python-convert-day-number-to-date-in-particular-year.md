# Python–将日期转换为特定年份的日期

> 原文:[https://www . geesforgeks . org/python-convert-day-number-to-date-in-special-year/](https://www.geeksforgeeks.org/python-convert-day-number-to-date-in-particular-year/)

给定日期，转换为它所指的日期。

> **输入**:Day _ num =“339”，year =“2020”
> **输出** : 12-04-2020
> **说明**:2020 年第 339 天是 12 月 4 日。
> 
> **输入**:Day _ num =“4”，year =“2020”
> **输出** : 01-04-2020
> **说明**:2020 年的第 4 天是 1 月 4 日。

**方法#1:使用 datetime.strptime()**

在这种情况下，我们获得年字符串和日数字字符串，并传递给 strptime()，转换为相应的所需日期。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert day number to date in particular year
# Using datetime.strptime()
from datetime import datetime

# initializing day number
day_num = "339"

# print day number
print("The day number : " + str(day_num))

# adjusting day num
day_num.rjust(3 + len(day_num), '0')

# Initialize year
year = "2020"

# converting to date
res = datetime.strptime(year + "-" + day_num, "%Y-%j").strftime("%m-%d-%Y")

# printing result
print("Resolved date : " + str(res))
```

**Output**

```py
The day number : 339
Resolved date : 12-04-2020

```

**方法 2:使用时间增量()**

在本例中，我们在 1 月 1 日之前初始化日期，然后使用 timedelta()添加天数，结果得到所需的日期。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert day number to date in particular year
# Using datetime.strptime()
from datetime import datetime, date, timedelta

# initializing day number
day_num = "339"

# print day number
print("The day number : " + str(day_num))

# adjusting day num
day_num.rjust(3 + len(day_num), '0')

# Initialize year
year = "2020"

# Initializing start date
strt_date = date(int(year), 1, 1)

# converting to date
res_date = strt_date + timedelta(days=int(day_num) - 1)
res = res_date.strftime("%m-%d-%Y")

# printing result
print("Resolved date : " + str(res))
```

**Output**

```py
The day number : 339
Resolved date : 12-04-2020

```