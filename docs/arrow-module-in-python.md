# Python 中的箭头模块

> 原文:[https://www.geeksforgeeks.org/arrow-module-in-python/](https://www.geeksforgeeks.org/arrow-module-in-python/)

Arrow 是一个用于处理日期和时间的 Python 模块。它为创建、操作、格式化和转换日期、时间和时间戳提供了一种明智且人性化的方法。它允许使用时区感知轻松创建日期和时间实例。

## 装置

箭头模块通过以下命令安装:

```
pip install arrow
```

## 特征

*   用户友好。
*   默认情况下为时区感知和世界协调时。
*   时区转换。
*   时间范围从微秒到年。
*   易于使用。
*   自动格式化和分析字符串。
*   支持越来越多的地区。

#### 获取世界协调时时间。

为了获得当前的世界协调时时间，我们使用 utcnow()方法。

## 蟒蛇 3

```
# importing arrow module
import arrow

# getting UTC time
utc_time = arrow.utcnow()

# printing the current UTC time
print('Current UTC Time is =', utc_time)
```

**输出:**

```
Current UTC Time is = 2020-02-28T18:06:39.228924+00:00
```

#### 获得印度时间。

为了得到当前区域(印度)时间，我们使用 now()方法。

## 蟒蛇 3

```
# importing arrow module
import arrow

# getting current indian time
ind_time = arrow.now('Asia/Calcutta')

# printing the time
print('Current India Time =', ind_time)
```

**输出:**

```
Current India Time = 2020-02-28T23:40:07.112695+05:30
```

#### 分析到目前为止的字符串

为了将字符串解析成日期格式，我们使用 get()方法。

## 蟒蛇 3

```
# importing arrow module
import arrow

# date in string format
s ='2020-02-02 12:30:45'

# parsing string into date
date = arrow.get(s, 'YYYY-MM-DD HH:mm:ss')

# printing the date
print(date)
```

**输出:**

```
2020-02-02T12:30:45+00:00
```

#### Unix 时间

Unix 时间是描述时间点的系统。它是自 Unix 纪元以来经过的秒数，即 1970 年 1 月 1 日世界协调时 00:00:00 的时间减去闰秒。

*   timestamp()方法用于获取 unix 时间。

*   fromtimestamp()方法，用于将 Unix 时间转换回箭头日期对象。

## 蟒蛇 3

```
# importing arrow module
import arrow

# getting current utc time
utc = arrow.utcnow()

# printing the unix time
print(utc)

# getting unix time
unix_time = utc.timestamp

# printing unix time
print(unix_time)

# converting unix time into arrow date object
date = arrow.Arrow.fromtimestamp(unix_time)

# printing arrow dateobject
print(date)
```

**输出:**

```
2020-03-04T13:33:15.041536+00:00
1583328795
2020-03-04T19:03:15+05:30
```

#### 日期时间中的箭头实例

箭头模块的实例也可以从日期时间模块创建。考虑下面的例子来更好地理解这个主题。

## 蟒蛇 3

```
# importing arrow module
import arrow

# importing datetime from datetime module
from datetime import datetime

# getting current time using datetime module
dt = datetime.now()

# creating arrow instance from datetime instance
arrow_dt = arrow.Arrow.fromdate(dt)

# printing datetime instance
print(dt)

# printing arrow instance
print(arrow_dt)
```

**输出:**

```
2020-03-04 19:16:04.317690
2020-03-04T00:00:00+00:00
```

#### 用于获取单个日期时间对象的属性

如果你想得到任何一个单独的对象，这里有一些可以使用的属性。

## 蟒蛇 3

```
#import arrow module
import arrow

#Call datetime functions that return properties
a = arrow.utcnow()
print(a.time())
print(a.date())

#Get any datetime value
print(a.year)
```

**输出:**

```
datetime.time(19, 16, 04, 317690)
datetime.date(2020, 3, 4)
2020
```

#### 替换和移位属性

如果您想单独替换或移动任何对象，这里有一些可以使用的属性。

## 蟒蛇 3

```
#import arrow module
import arrow

# getting current utc time
a = arrow.utcnow()

# printing the unix time without alteration
print("without alteration: ",a)

# replacing only the hours to 5 and minutes to 30
b = a.replace(hour=5, minute=30)
print("with hours and minutes replaced: ",b)

# shifting forward in weeks
c = a.shift(weeks=+3)
print("with weeks shifted 3 forward: ",c)

# replacing only the timezone
d = a.replace(tzinfo='US/Pacific')
print("with timezone replaced: ",d)
```

**输出:**

```
without alteration: 2020-03-04T13:33:15.041536+00:00
with hours and minutes replaced: 2020-03-04T05:30:15.041536+00:00
with weeks shifted 3 forward: 2020-03-25T13:33:15.041536+00:00
with timezone replaced: 2020-03-04T13:33:15.041536-07:00 
```

#### 人性化的格式

以上所有的属性和功能输出更像是一种计算机格式，但是如果你想让它更像一种人类的形式呢？例如:“一小时前”或“2 小时前”，这里有一些属性可以用来实现人性化的格式。

## 蟒蛇 3

```
#import arrow module
import arrow

#Humanize to past
apast = arrow.utcnow().shift(hours=-1)
print(apast.humanize())

#humanize to future
present = arrow.utcnow()
afuture = present.shift(hours=3)
print(afuture.humanize(present))

#Indicate a specific time granularity
afuture = present.shift(minutes=73)
print(afuture.humanize(present, granularity="minute"))
print(afuture.humanize(present, granularity=["hour", "minute"]))
```

**输出:**

```
'an hour ago'
'in 3 hours'
'in 73 minutes'
'in an hour and 13 minutes'
```