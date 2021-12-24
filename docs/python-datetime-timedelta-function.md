# Python | datetime.timedelta()函数

> 原文:[https://www . geesforgeks . org/python-datetime-time delta-function/](https://www.geeksforgeeks.org/python-datetime-timedelta-function/)

Python **`timedelta()`** 函数存在于*日期时间库*下，一般用于计算日期差异，也可以用于 Python 中的日期操作。这是执行日期操作最简单的方法之一。

> **语法:** datetime.timedelta(天=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)
> 
> **返回:**日期

**代码#1:**

```py
# Timedelta function demonstration 

from datetime import datetime, timedelta

# Using current time
ini_time_for_now = datetime.now()

# printing initial_date
print ("initial_date", str(ini_time_for_now))

# Calculating future dates
# for two years
future_date_after_2yrs = ini_time_for_now + \
                        timedelta(days = 730)

future_date_after_2days = ini_time_for_now + \
                         timedelta(days = 2)

# printing calculated future_dates
print('future_date_after_2yrs:', str(future_date_after_2yrs))
print('future_date_after_2days:', str(future_date_after_2days))
```

**Output:**

```py
initial_date 2019-02-27 12:41:45.018389
future_date_after_2yrs: 2021-02-26 12:41:45.018389
future_date_after_2days: 2019-03-01 12:41:45.018389

```

**代码#2:**

```py
# Timedelta function demonstration 
from datetime import datetime, timedelta

# Using current time
ini_time_for_now = datetime.now()

# printing initial_date
print ("initial_date", str(ini_time_for_now))

# Calculating past dates
# for two years
past_date_before_2yrs = ini_time_for_now - \
                       timedelta(days = 730)

# for two hours
past_date_before_2hours = ini_time_for_now - \
                        timedelta(hours = 2)

# printing calculated past_dates
print('past_date_before_2yrs:', str(past_date_before_2yrs))
print('past_date_after_2days:', str(past_date_before_2hours))
```

**Output:**

```py
initial_date 2019-02-27 12:41:46.104662
past_date_before_2yrs: 2017-02-27 12:41:46.104662
past_date_after_2days: 2019-02-27 10:41:46.104662

```

**代码#3:**

```py
# Timedelta function demonstration 
from datetime import datetime, timedelta

# Using current time
ini_time_for_now = datetime.now()

# printing initial_date
print ("initial_date", str(ini_time_for_now))

# Some another datetime
new_final_time = ini_time_for_now + \
                 timedelta(days = 2)

# printing new final_date
print ("new_final_time", str(new_final_time))

# printing calculated past_dates
print('Time difference:', str(new_final_time - \
                             ini_time_for_now))
```

**Output:**

```py
initial_date 2019-02-27 12:41:47.386595
new_final_time 2019-03-01 12:41:47.386595
Time difference: 2 days, 0:00:00

```