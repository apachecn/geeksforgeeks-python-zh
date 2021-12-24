# 如何在 Python 中将 DateTime 转换为 UNIX 时间戳？

> 原文:[https://www . geesforgeks . org/how-convert-datetime-to-UNIX-timestamp-in-python/](https://www.geeksforgeeks.org/how-to-convert-datetime-to-unix-timestamp-in-python/)

Unix 时间戳是一个每秒增加 1 的单符号整数，允许计算机存储和操作传统的日期系统。软件然后被翻译成人类可读的格式。Unix 时间戳是自 1970 年 1 月 1 日起计算的秒数。在本文中，我们将看到如何将 DateTime 转换为 Unix 时间戳。

## DateTime 到 Unix 时间戳

为了将 Python datetime 转换为 Unix 时间戳，我们在本例中导入了一个名为 DateTime 和 Time 的模块，变量 date_time 已经声明并分配了 DateTime。时间/日期(2021 年 7 月 26 日 21 日 20 时)。年是 2021 年，月是 7，日是 26，小时是 21，分钟是 20。

**代码:**

## 蟒蛇 3

```py
# importing datetime module
import datetime
import time

# assigned regular string date
date_time = datetime.datetime(2021, 7, 26, 21, 20)

# print regular python date&time
print("date_time =>",date_time)

# displaying unix timestamp after conversion
print("unix_timestamp => ",
      (time.mktime(date_time.timetuple())))
```

**输出:**

```py
date_time => 2021-07-26 21:20:00
unix_timestamp =>  1627314600.0
```

**说明:**

日期和时间操作类由日期时间模块提供。当地时间的反函数是 mktime()。它接受结构时间或完整的 9 元组作为参数，并返回一个与时间()兼容的浮点数。它还用于将日期时间转换为 Unix 时间戳。

datetime.date 对象的 timetuple()方法返回一个 time 对象. struct time。struct time 对象是一个命名元组，可以使用索引或名称进行检索。timetuple()函数返回的命名元组的年、月和日字段将根据 date 对象设置，而小时、分钟和秒字段将设置为零。

## 日期时间到 13 位的 Unix 时间戳

若要获取当前时间，请使用 datetime.now()。datetime 类的 timetuple()函数以命名元组的形式返回 datetime 的属性。13 位时间戳必须乘以 1000。

**代码:**

## 蟒蛇 3

```py
import time
import datetime

presentDate = datetime.datetime.now()
unix_timestamp = datetime.datetime.timestamp(presentDate)*1000
print(unix_timestamp)
```

**输出:**

```py
1628497724509.293
```

## 以世界协调时时区表示的日期时间到 Unix 时间戳

日历模块提供了有用的日历相关功能。函数的作用是:返回世界协调时时区的当前时间。在时间模块中，timegm 函数返回一个 Unix 时间戳。datetime 类的 timetuple()函数以命名元组的形式返回 datetime 的属性。要获取 Unix 时间戳，请使用打印时间(UTC)。

**代码:**

## 蟒蛇 3

```py
import calendar
import datetime

date = datetime.datetime.utcnow()
utc_time = calendar.timegm(date.utctimetuple())
print(utc_time)
```

**输出:**

```py
1628497783
```

## DateTime 到 Unix 时间戳毫秒

datetime.now()函数用于获取当前时间。mktime 方法是一种时间方法，是当地时间的反函数；它用于将 datetime 转换为 Unix 时间戳毫秒。datetime 类的 timetuple()函数以命名元组的形式返回 datetime 的属性。要获得以毫秒为单位的时间，将其乘以 1000。

**代码:**

## 蟒蛇 3

```py
import datetime
import time

ms = datetime.datetime.now()
print(time.mktime(ms.timetuple()) * 1000)
```

**输出:**

```py
1628497823000.0
```

## Datetime.date 到 Unix 时间戳

time.date()是一个只接受日期的函数。在这种情况下，2021 年是年，8 是月，6 是日。mktime()是一种时间方法，它是本地时间的反函数；它用于将日期转换为 Unix 时间戳。

**代码:**

## 蟒蛇 3

```py
import datetime
import time

datetime = datetime.date(2021, 8, 6)
print("Unix_Time: ",
      (time.mktime(datetime.timetuple())))
```

**输出:**

```py
Unix_Time:  1628188200.0
```

## Unix 时间戳的日期时间字符串

在这种情况下，日期和时间以字符串格式提供。这里，8 表示月，6 表示日，2021 表示年，05 表示小时，54 表示分，8 表示秒。strptime()是一个 datetime 模块方法，用于将字符串转换为 datetime 和 time 对象。timestamp()函数返回当前位置的当前时间。

**代码:**

## 蟒蛇 3

```py
import datetime

date_example = "8/6/2021, 05:54:8"
date_format = datetime.datetime.strptime(date_example,
                                         "%m/%d/%Y, %H:%M:%S")
unix_time = datetime.datetime.timestamp(date_format)
print(unix_time)
```

**输出:**

```py
1628209448.0
```

## Unix 时间戳到 Python 日期时间

Python 中的 DateTime 模块用于处理 Python 中与日期和时间相关的问题。fromtimestamp()方法是此模块中包含的函数之一。date 类的函数 fromtimestamp()计算并返回对应于指定时间戳的日期。允许的时间戳范围从 1970 年到 2038 年。如果时间戳中有闰秒，fromtimestamp()函数将忽略它们。

首先，我们从 datetime 模块导入 datetime 类。然后，UNIX 值对象存储在一个变量中。然后我们使用 datetime.fromtimestamp()方法来检索时间和日期。

strftime()函数是 datetime 模块中的另一个函数。该函数有助于以特定格式返回日期时间。此函数用于将日期和时间对象转换为字符串表示形式。上述代码中的格式代码为%d、%m、%Y、%H、%M 和%S，分别表示日、月、年、小时、分钟和秒。

**代码:**

## 蟒蛇 3

```py
# importing datetime module
import datetime

# assigned unix time
unix_time = 1627334400

date_time = datetime.datetime.fromtimestamp(unix_time)

# print unix time stamp
print("Unix_Time =>",unix_time)

# displaying date and time in a regular
# string format
print("Date & Time =>" ,
      date_time.strftime('%Y-%m-%d %H:%M:%S'))
```

**输出:**

```py
Unix_Time => 1627334400
Date & Time => 2021-07-27 02:50:00
```