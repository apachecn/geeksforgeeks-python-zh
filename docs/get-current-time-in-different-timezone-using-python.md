# 使用 Python 获取不同时区的当前时间

> 原文:[https://www . geesforgeks . org/get-current-time-in-different-time-in-time-time-in-time-different-time-time-in-time-time-time-time-time-time-time-time-time-time-time-time-time-time-time-](https://www.geeksforgeeks.org/get-current-time-in-different-timezone-using-python/)

时区被定义为一个地理区域或地区，标准时间贯穿其中。它基本上是指一个地区或国家的当地时间。大多数时区都偏离了世界时区标准协调世界时。
为了得到不同时区的当前时间，我们将使用`pytz` python 库。

### 如何获取当前时间？

为了得到当地时间，我们可以使用时间模块。时间模块的一些重要功能

*   ***【local time()***–有助于获取当前的当地时间
*   ***str time(" % H:% M:% S "，t)***–它有助于决定用于显示时间的时间格式

### 如何获取不同区域的当前时间？

为了获得特定时区的当前时间，需要使用`pytz` Python 库。pytz 库的一些重要命令如下

*   ***【utc】***–这有助于获得标准的 UTC 时区
*   ***时区()***–它有助于获取特定位置的时区
*   ***现在()***–它有助于以默认格式获取日期、时间、utc 标准
*   ***astimezone()***–它有助于将特定时区的时间转换为另一个时区

**示例:**

```py
import time

curr_time = time.localtime()
curr_clock = time.strftime("%H:%M:%S", curr_time)

print(curr_clock)
```

**输出:**

```py
11:58:19

```

我们将获得该地区的当地当前时间和标准 UTC 时间
**示例:**

```py
from datetime import datetime
import pytz

# get the standard UTC time 
UTC = pytz.utc

# it will get the time zone 
# of the specified location
IST = pytz.timezone('Asia/Kolkata')

# print the date and time in
# standard format
print("UTC in Default Format : ", 
      datetime.now(UTC))

print("IST in Default Format : ", 
      datetime.now(IST))

# print the date and time in 
# specified format
datetime_utc = datetime.now(UTC)
print("Date & Time in UTC : ",
      datetime_utc.strftime('%Y:%m:%d %H:%M:%S %Z %z'))

datetime_ist = datetime.now(IST)
print("Date & Time in IST : ", 
      datetime_ist.strftime('%Y:%m:%d %H:%M:%S %Z %z'))
```

```py
Output:
UTC in Default Format :  2020-03-31 07:15:59.640418+00:00
IST in Default Format :  2020-03-31 12:45:59.692642+05:30
Date & Time in UTC :  2020:03:31 07:15:59 UTC+0000
Date & Time in IST :  2020:03:31 12:45:59 IST+0530

```

比较不同地区时区的 UTC 和 IST 格式
**示例:**

```py
from datetime import datetime
import pytz

UTC = pytz.utc

timeZ_Kl = pytz.timezone('Asia/Kolkata') 
timeZ_Ny = pytz.timezone('America/New_York')
timeZ_Ma = pytz.timezone('Africa/Maseru')
timeZ_Ce = pytz.timezone('US/Central')
timeZ_At = pytz.timezone('Europe/Athens')

dt_Kl = datetime.now(timeZ_Kl)
dt_Ny = datetime.now(timeZ_Ny)
dt_Ma = datetime.now(timeZ_Ma)
dt_Ce = datetime.now(timeZ_Ce)
dt_At = datetime.now(timeZ_At)

utc_Kl = dt_Kl.astimezone(UTC)
utc_Ny = dt_Ny.astimezone(UTC)
utc_Ma = dt_Ma.astimezone(UTC)
utc_Ce = dt_Ce.astimezone(UTC)
utc_At = dt_At.astimezone(UTC)

print("UTC Format \t\t\t  IST Format")

print(utc_Kl.strftime('%Y-%m-%d %H:%M:%S %Z %z'),
      "\t ",
      dt_Kl.strftime('%Y-%m-%d %H:%M:%S %Z %z'))

print(utc_Ny.strftime('%Y-%m-%d %H:%M:%S %Z %z'),
      "\t ",
      dt_Kl.strftime('%Y-%m-%d %H:%M:%S %Z %z'))

print(utc_Ma.strftime('%Y-%m-%d %H:%M:%S %Z %z'),
      "\t ",
      dt_Kl.strftime('%Y-%m-%d %H:%M:%S %Z %z'))

print(utc_Ce.strftime('%Y-%m-%d %H:%M:%S %Z %z'),
      "\t ",
      dt_Kl.strftime('%Y-%m-%d %H:%M:%S %Z %z'))

print(utc_At.strftime('%Y-%m-%d %H:%M:%S %Z %z'),
      "\t ",
      dt_Kl.strftime('%Y-%m-%d %H:%M:%S %Z %z'))
```

```py
Output:
UTC Format               IST Format
2020-03-31 11:21:13 UTC +0000       2020-03-31 16:51:13 IST +0530
2020-03-31 11:21:13 UTC +0000       2020-03-31 16:51:13 IST +0530
2020-03-31 11:21:13 UTC +0000       2020-03-31 16:51:13 IST +0530
2020-03-31 11:21:13 UTC +0000       2020-03-31 16:51:13 IST +0530
2020-03-31 11:21:13 UTC +0000       2020-03-31 16:51:13 IST +0530

```

因此，我们可以得出结论，虽然不同地区有不同的地区时区，但当转换为世界协调时时区时，它们都给出了相同的值。因此我们可以说

*   IST 比世界协调时早+0530 小时
*   美国东部时间是世界协调时前-0400 小时
*   SAST 比世界协调时早+0200 小时
*   协调世界时前 5:00
*   EEST 比世界协调时早+0300 小时