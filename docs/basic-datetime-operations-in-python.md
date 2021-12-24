# Python 中的基本日期时间操作

> 原文:[https://www . geesforgeks . org/basic-datetime-operations-in-python/](https://www.geeksforgeeks.org/basic-datetime-operations-in-python/)

Python 有一个名为 DateTime 的内置模块，以多种方式处理日期和时间。在本文中，我们将看到 Python 中的基本日期时间操作。

在下面提到的日期时间模块中，有六个主要对象类及其各自的组件:

1.  日期时间.日期
2.  日期时间.时间
3.  datetime.datetime
4.  datetime.tzinfo
5.  日期时间. 时间德尔塔
6.  日期时间.时区

现在我们将看到上面提到的 datetime 模块下每个函数的程序。

### datetime.date（）：

我们可以从日期类中生成日期对象。date 对象表示具有年、月和日的日期。

> **语法:** datetime.date(年、月、日)

**str time 以各种格式打印日、月、年。以下是其中一些:**

*   **current . str time(" % m/% d/% y ")**，以**月(数字)/日/年**格式打印
*   **current . str time(" % b-% d-% Y ")**，以**月(缩写)-日-年**格式打印
*   以**日期/月/年**格式打印的**current . str time(" % d/% m/% Y ")**
*   **current . str time(" % B % d，%Y")** ，以**月(字)日、年**格式打印

## 蟒蛇 3

```py
from datetime import date

# You can create a date object containing
# the current date
# by using a classmethod named today()
current = date.today()

# print current year, month, and year individually
print("Current Day is :", current.day)
print("Current Month is :", current.month)
print("Current Year is :", current.year)

# strftime() creates string representing date in
# various formats
print("\n")
print("Let's print date, month and year in different-different ways")
format1 = current.strftime("%m/%d/%y")

# prints in month/date/year format
print("format1 =", format1)

format2 =  current.strftime("%b-%d-%Y")
# prints in month(abbreviation)-date-year format
print("format2 =", format2)

format3 = current.strftime("%d/%m/%Y")

# prints in date/month/year format
print("format3 =", format3)

format4 =  current.strftime("%B %d, %Y")

# prints in month(words) date, year format
print("format4 =", format4)
```

**输出:**

```py
Current Day is : 23
Current Month is : 3
Current Year is : 2021

Let's print date, month and year in different-different ways
format1 = 03/23/21
format2 = Mar-23-2021
format3 = 23/03/2021
format4 = March 23, 2021
```

### datetime.time（）：

从时间类生成的时间对象表示本地时间。

**组件:**

*   小时
*   分钟
*   第二
*   微秒
*   齐 info

> **语法:** datetime.time(小时、分钟、秒、微秒)

**代码:**

## 蟒蛇 3

```py
from datetime import time

# time() takes hour, minutes, second,
# microsecond respectively in order
# if no parameter is passed in time() by default
# it takes 0
defaultTime = time()

print("default_hour =", defaultTime.hour)
print("default_minute =", defaultTime.minute)
print("default_second =", defaultTime.second)
print("default_microsecond =", defaultTime.microsecond)

# passing parameter in different-different ways
# hour, minute and second respectively is a default
# order
time1= time(10, 5, 25)
print("time_1 =", time1)

# assigning hour, minute and second to respective
# variables
time2= time(hour = 10, minute = 5, second = 25)
print("time_2 =", time2)

# assigning hour, minute, second and microsecond to
# respective variables
time3= time(hour=10, minute= 5, second=25, microsecond=55)
print("time_3 =", time3)
```

输出:

```py
default_hour = 0
default_minute = 0
default_second = 0
default_microsecond = 0
time_1 = 10:05:25
time_2 = 10:05:25
time_3 = 10:05:25.000055
```

### datetime.datetime（）：

datetime.datetime()模块显示日期和时间的组合。

**组件:**

*   年
*   月
*   天
*   小时
*   分钟
*   第二，
*   微秒
*   齐 info

> **语法:** datetime.datetime(年、月、日)
> 
> 或者
> 
> datetime.datetime(年、月、日、小时、分钟、秒、微秒)

**以不同方式使用 strftime()方法的当前日期和时间:**

*   **str time(" % d ")**给出当天
*   **str time(" % m ")**给出当前月份
*   **str time(" % Y ")**给出当前年份
*   **str time(" % H:% M:% S ")**以小时、分钟和秒的格式给出当前时间
*   **str time(" % M/% d/% Y，%H:%M:%S")** 一起给出日期和时间

**代码:**

## 蟒蛇 3

```py
from datetime import datetime

# now() gives current date and time
current = datetime.now()

# print combinedly
print(current)
print("\n")
print("print each term individually")

day = current.strftime("%d")

# print day
print("day:", day)

month = current.strftime("%m")

# print month
print("month:", month)

year = current.strftime("%Y")

# print year
print("year:", year)

time = current.strftime("%H:%M:%S")

# time in hour, minute and second
print("time:", time)

print("\n")
print("printing date and time together")
date_time = current.strftime("%m/%d/%Y, %H:%M:%S")
print("date and time:", date_time)
print("\n")

# fetching details from timestamp
timestamp = 1615797322
date_time = datetime.fromtimestamp(timestamp)

# %c, %x and %X are used for locale's proper date and time representation
time_1 = date_time.strftime("%c")
print("first_output:", time_1)

time_2 = date_time.strftime("%x")
print("second_output:", time_2)

time_3 = date_time.strftime("%X")
print("third_output:", time_3)

print("\n")

# assigning each term manually
manual = datetime(2021, 3, 28, 23, 55, 59, 342380)
print("year =", manual.year)
print("month =", manual.month)
print("hour =", manual.hour)
print("minute =", manual.minute)
print("timestamp =", manual.timestamp())
```

输出:

```py
2021-03-23 19:00:20.726833

print each term individually
day: 23
month: 03
year: 2021
time: 19:00:20

printing date and time together
date and time: 03/23/2021, 19:00:20

first_output: Mon Mar 15 14:05:22 2021
second_output: 03/15/21
third_output: 14:05:22

year = 2021
month = 3
hour = 23
minute = 55
timestamp = 1616955959.34238
```

### datetime.timedelta（）：

它显示一个持续时间，表示两个日期、时间或日期时间实例到微秒分辨率之间的差异。

在这里，我们实现了一些基本功能，并打印了过去和未来的日子。此外，我们还将打印 timedelta max、min 和 resolution 的其他一些属性，分别显示最大天数和时间、最小日期和时间，以及非相等 timedelta 对象之间的最小可能差异。这里我们还将在两个不同的日期和时间应用一些算术运算。

## 蟒蛇 3

```py
from datetime import timedelta, datetime

present_date_with_time = datetime.now()

print("Present Date :", present_date_with_time)

# coming date after 10 days
ten_days_after= present_date_with_time + timedelta(days = 10)
print('Date after 10 days :',ten_days_after)

# date before 10 days
ten_days_before= present_date_with_time - timedelta(days = 10)
print('Date before 10 days :',ten_days_before)

# date before one year ago
one_year_before_today= present_date_with_time + timedelta(days = 365)
print('One year before present Date :', one_year_before_today)

#date before one year ago
one_year_after_today= present_date_with_time - timedelta(days = 365)
print('One year before present Date :', one_year_after_today)

print("\n")
print("print some other attributes of timedelta\n")

# maximum days and time
print("Max : ",timedelta.max)

# minimum days and time
print("Min : ",timedelta.min)

# The smallest possible difference between non-equal
# timedelta objects, timedelta(microseconds=1)
print("Resolution: ",timedelta.resolution)

print('Total number of seconds in an year :',
      timedelta(days = 365).total_seconds())

print("\nApply some operations on timedelta function\n")
time_after_one_min = present_date_with_time + timedelta(seconds=10) * 6
print('Time after one minute :', time_after_one_min)

print('Timedelta absolute value :', abs(timedelta(days = +20)))

print('Timedelta string representation :', str(timedelta(days = 5,
                       seconds = 40, hours = 20, milliseconds = 355)))

print('Timedelta object representation :', repr(timedelta(days = 5,
                       seconds = 40, hours = 20, milliseconds = 355)))
```

输出:

> 目前日期:2021-03-25 22:34:27.651128
> 
> 10 天后日期:2021-04-04 22:34:27.651128
> 
> 10 日前日期:2021-03-15 22:34:27.651128
> 
> 现在日期前一年:2022-03-25 22:34:27.651121281025
> 
> 现在日期前一年:2020-03-25 22:34:27.651121281025
> 
> 打印时间增量的一些其他属性
> 
> 最大值:999999999 天，23:59:59.9999999
> 
> 分钟:-999999999 天，0:00:00
> 
> 分辨率:0:00:00.000001
> 
> 一年中的总秒数:31536000.0
> 
> 对时间增量函数应用一些操作
> 
> 一分钟后时间:2021-03-25 22:35:27.651128
> 
> 时间增量绝对值:20 天，0:00:00
> 
> 时间增量字符串表示:5 天，20:00:40.355000
> 
> Timedelta 对象表示:datetime.timedelta(天数=5，秒=72040，微秒=355000)

### datetime.tzinfo():

它是时区信息对象的抽象基类。日期时间和时间类使用它们来提供可定制的时间调整概念。

tzinfo 基类有以下四种方法可用:

*   **utcoffset(self，dt):** 返回作为参数传递的日期时间实例的偏移量
*   **夏令时(自我，dt):** 夏令时代表夏令时。夏令时表示在夏天将时钟提前 1 小时，这样黑暗会根据时钟晚些时候降临。它被设置为开或关。根据以下要素进行检查:

> (dt.year，dt.month，dt.day，dt.hour，dt.minute，dt.second，dt.weekday()，0，0)

*   **tzname(self，dt):** 它返回一个 Python String 对象。它用于查找传递的 datetime 对象的时区名称。
*   **fromutc(self，dt) :** 此函数返回等效的本地时间，并采用 utc 中对象的日期和时间。它主要用于调整日期和时间。它是从默认的 datetime.astimezone()实现中调用的。dt.tzinfo 将作为自身传递，dst 日期和时间数据将作为等效的本地时间返回。

**注意:**如果 dt.tzinfo 不是 self 或/和 dst()是 None，它将引发 ValueError。

## 蟒蛇 3

```py
# code
from datetime import datetime, timedelta
from pytz import timezone
import pytz

time_zone = timezone('Asia/Calcutta')

normal = datetime(2021, 3, 16)
ambiguous = datetime(2021, 4, 16, 23, 30)

# is_dst parameter is ignored for most of the
# timstamps.It is only used during DST
# transition ambiguous periods to resolve that
# ambiguity
print("Operations on normal datetime")
print(time_zone.utcoffset(normal, is_dst=True))
print(time_zone.dst(normal, is_dst=True))
print(time_zone.tzname(normal, is_dst=True))

# put is_dst=False
print(time_zone.utcoffset(normal, is_dst=False))
print(time_zone.dst(normal, is_dst=False))
print(time_zone.tzname(normal, is_dst=False))

print("\n")
print("Operations on ambiguous datetime")
print(time_zone.utcoffset(ambiguous, is_dst=True))
print(time_zone.dst(ambiguous, is_dst=True))
print(time_zone.tzname(ambiguous, is_dst=True))

# is_dst=False
print(time_zone.utcoffset(ambiguous, is_dst=False))
print(time_zone.dst(ambiguous, is_dst=False))
print(time_zone.tzname(ambiguous, is_dst=False))
```

**Output**

```py
Operations on normal datetime
5:30:00
0:00:00
IST
5:30:00
0:00:00
IST

Operations on ambiguous datetime
5:30:00
0:00:00
IST
5:30:00
0:00:00
IST
```

输出:

```py
Operations on normal datetime
5:30:00
0:00:00
IST
5:30:00
0:00:00
IST

Operations on ambiguous datetime
5:30:00
0:00:00
IST
5:30:00
0:00:00
IST
```

### datetime.timezone（）：

描述:它是一个实现 tzinfo 抽象基类的类，作为 UTC 的固定偏移量。

> **语法:** datetime.timezone()

## 蟒蛇 3

```py
from datetime import datetime, timedelta
from pytz import timezone
import pytz

utc = pytz.utc
print(utc.zone)

india = timezone('Asia/Calcutta')
print(india.zone)

eastern = timezone('US/Eastern')
print(eastern.zone)

time_format = '%Y-%m-%d %H:%M:%S %Z%z'

# localize() is used to localize
# datetime with no timezone information
loc_dt = india.localize(datetime(2021, 3, 16, 6, 0, 0))
loc_dt = india.localize(datetime(2021, 3, 16, 6, 0, 0))
print(loc_dt.strftime(time_format))

# another way of building a localized time is by converting
# an existing localized time
# using the standard astimezone() method
eastern_dt = loc_dt.astimezone(eastern)
print(eastern_dt.strftime(time_format))

print(datetime(2021, 3, 16, 12, 0, 0, tzinfo=pytz.utc).strftime(time_format))

# 10 minutes before
before_dt = loc_dt - timedelta(minutes=10)
print(before_dt.strftime(time_format))
print(india.normalize(before_dt).strftime(time_format))

# 20 mins later
after_dt = india.normalize(before_dt + timedelta(minutes=20))
print(after_dt.strftime(time_format))
```

输出:

```py
UTC
Asia/Calcutta
US/Eastern
2021-03-16 06:00:00 IST+0530
2021-03-15 20:30:00 EDT-0400
2021-03-16 12:00:00 UTC+0000
2021-03-16 05:50:00 IST+0530
2021-03-16 05:50:00 IST+0530
2021-03-16 06:10:00 IST+0530
```

### 让我们看看不同的函数，并在时间模块下进行描述:-

<figure class="table">

| 

### Function

 | 

### Description

 |
| --- | --- |
| 时间( ) | 以秒为单位返回浮点数的时间 |
| ctime() | 返回当前日期和时间 |
| 睡眠( ) | 在给定的持续时间内停止线程的执行 |
| localtime() | 以 time.struct_time 格式返回日期和时间 |
| gmtime（ ） | 以世界协调时格式返回时间 |
| mktime（ ） | 返回自输出纪元以来经过的秒数 |
| asctime（ ） | 返回表示相同的字符串 |

</figure>

**现在我们将在表格中看到上述每个功能的程序和输出。**

**1: time()方法:**time()方法返回自纪元以来以秒为单位的浮点数形式的时间，单位为 UTC。

> **语法:** time.time([ ])
> 
> 注意:它没有任何参数

## 蟒蛇 3

```py
# import time
import time

#prints total number of seconds passed since epoch
print(time.time())
```

输出:

```py
1616692391.3081982
```

**2: ctime()方法**

ctime()方法将自纪元以来以秒表示的时间转换为表示本地时间的字符串。如果未提供秒或无，则使用时间()返回的当前时间。这个方法相当于 as time(local time(秒))。ctime()方法不使用区域设置信息。

> **语法:** time.ctime([秒])
> 
> 其中作为参数传递的秒是要转换为字符串表示形式的秒数。

## 蟒蛇 3

```py
import time

number_of_seconds=1625925769.9618232

# function takes seconds passed since epoch as an argument and returns
# a string representing local time
print(time.ctime(number_of_seconds))
```

Output

```py
Sat Jul 10 14:02:49 2021
```

**3:睡眠( )方法**

Python time 方法 sleep()在给定的秒数内停止执行。数字的浮点数可以作为参数传递，以获得更精确的睡眠时间。

> **语法:** time.sleep([秒])
> 
> 其中作为参数传递的 sec 是
> 
> 该过程将被停止。

## 蟒蛇 3

```py
import time

# prints GEEKSFORGEEKS immediately
print("GEEKSFORGEEKS")

time.sleep(1.23)

# prints GEEKSFORGEEKS after 1.23 seconds
# as it stops execution for that time interval
print("GEEKSFORGEEKS")
```

Output

```py
GEEKSFORGEEKS
GEEKSFORGEEKS
```

**4: localtime()方法**

localtime()方法将秒数转换为本地时间。如果未提供秒或无，则使用时间()返回的当前时间。当夏令时适用于给定时间时，夏令时标志设置为 1。

> **语法:** time.localtime([秒])
> 
> 其中作为参数传递的 sec 是要转换为 struct_time 表示形式的秒数。

## 蟒蛇 3

```py
import time

# returns a time.struct_time
# object with a named tuple interface
print(time.localtime())
```

输出

> time.struct_time(tm_year=2021，tm_mon=3，tm_mday=30，tm_hour=8，tm_min=48，tm_sec=58，tm_wday=1，tm_yday=89，tm_isdst=0)

**5: gmtime()方法。**

gmtime()方法将自 Epoch 以来以秒表示的时间转换为以 UTC 表示的 struct_time，其中 dst 标志始终为零。如果未提供秒或无，则使用时间()返回的当前时间。

> **语法:** time.gmtime([秒])
> 
> 其中，作为参数传递的 sec 是要转换为 structure _ time 表示形式的秒数。

## 蟒蛇 3

```py
# code
import time
# returns a time.struct_time object with a named tuple interface
# If secs is not provided or None,
# the current time as returned by time() is used
print(time.gmtime())
```

输出:

> time.struct_time(tm_year=2021，tm_mon=3，tm_mday=30，tm_hour=8，tm_min=49，tm_sec=18，tm_wday=1，tm_yday=89，tm_isdst=0)

**6: mktime()方法**

它是 localtime()方法的反函数。它将一个参数作为 struct_time 或完整的 9 元组，并返回一个浮点数。如果输入值未表示为有效时间，则会引发 OverflowError 或 ValueError。

> **语法:** time.mktime([t])
> 
> 其中作为参数传递的 t 是 time.struct_time 对象或包含 9 个对应于 time.struct_time 对象的元素的元组

## 蟒蛇 3

```py
# code
import time

# method mktime() is the inverse function of localtime()
# Its argument is the struct_time or full 9-tuple and
# it returns a floating point number, for compatibility with time().

t = (2016, 2, 15, 10, 13, 38, 1, 48, 0)
d = time.mktime(t)
print ("time.mktime(t) : %f" %  d)
print ("asctime(localtime(secs)): %s" % time.asctime(time.localtime(d)))
```

Output

```py
time.mktime(t) : 1455531218.000000
asctime(localtime(secs)): Mon Feb 15 10:13:38 2016
```

**7: asctime()方法**

Python time 方法 as time()将表示由 gmtime()或 localtime()返回的时间的 struct_time 转换为以下格式的 24 个字符的字符串:“2021 年 3 月 23 日星期二 23:21:05”。

> **语法:** time.asctime([t])
> 
> 其中作为参数传递的 t 是 9 个元素的元组或 struct_time，表示由 gmtime()或 localtime()函数返回的时间。

## 蟒蛇 3

```py
import time
# method returns 24-character string of
# the following form − 'Mon March 15 23:21:05 2021'

local_time = time.localtime()
print ("asctime : ",time.asctime(local_time))
```

Output

```py
asctime :  Tue Mar 16 06:02:42 2021
```