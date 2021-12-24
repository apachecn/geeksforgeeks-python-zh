# 使用 Python 获取当前时间戳

> 原文:[https://www . geesforgeks . org/get-current-timestamp-using-python/](https://www.geeksforgeeks.org/get-current-timestamp-using-python/)

时间戳是一系列字符或编码信息，用于查找特定事件发生的时间，通常给出一天中的日期和时间，精确到一秒钟的一小部分。在本文中，我们将学习如何在 Python 中**获取当前时间戳**。

Python 中获取当前时间戳有不同的方式，我们可以使用模块*时间、日期时间*和*日历*的函数。

**1。使用模块时间:**
*时间*模块提供各种与时间相关的功能。函数 time 以浮点数形式返回自纪元以来的时间(以秒为单位)。epoch 被定义为时间开始的点，并且依赖于平台。

```
Syntax: time.time()
Parameters: NA
Return: floating point number expressed in seconds.
```

```
# using time module
import time

# ts stores the time in seconds
ts = time.time()

# print the current timestamp
print(ts)
```

**输出:**

```
1594819641.9622827
```

**2。使用模块日期时间:**
*日期时间*模块提供用于操作日期和时间的类。
虽然支持日期和时间算法，但实现的目标是高效的属性提取，用于输出格式化和操作。函数 datetime.datetime.now 返回自纪元以来的秒数。

```
Syntax: datetime.now()
Parameters: tz (time zone) which is optional.
Return: the current local date and time.
```

```
# using datetime module
import datetime;

# ct stores current time
ct = datetime.datetime.now()
print("current time:-", ct)

# ts store timestamp of current time
ts = ct.timestamp()
print("timestamp:-", ts)
```

**输出:**

```
current time:- 2020-07-15 14:30:26.159446
timestamp:- 1594823426.159446
```

**3。使用模块日历:**
我们还可以通过组合多个模块的多个功能来获取时间戳。在本文中，我们将使用函数 calendar.timegm 来转换表示当前时间的元组。

```
Syntax: calendar.timegm(tuple)
Parameters: takes a time tuple such as returned by the gmtime() function in the time module.
Return: the corresponding Unix timestamp value.
```

```
# using calendar module
# using time module
import calendar;
import time;

# gmt stores current gmtime
gmt = time.gmtime()
print("gmt:-", gmt)

# ts stores timestamp
ts = calendar.timegm(gmt)
print("timestamp:-", ts)
```

**输出:**

> GMT:-time . struct _ time(TM _ year = 2020，tm_mon=7，tm_mday=15，tm_hour=19，tm_min=21，tm_sec=6，tm_wday=2，tm_yday=197，tm_isdst=0)
> 时间戳:- 1594840866