# Python 日期时间到整数时间戳

> 原文:[https://www . geesforgeks . org/python-datetime-to-integer-timestamp/](https://www.geeksforgeeks.org/python-datetime-to-integer-timestamp/)

在本文中，我们将看到如何将 python DateTime 转换为整数时间戳。

timestamp()函数返回自 1970 年 1 月 1 日以来经过的秒数。那个零时刻被称为纪元。首先，我们将获得当前时间，或者明确提到我们想要时间戳的所需日期和时间。有几种方法可以得到日期和时间。我们将在浏览示例时看到它们。然后我们使用 timestamp()函数将**日期时间转换为时间戳**。

最后，我们将以秒和毫秒为单位舍入时间戳，并显式地将其类型转换为整数数据类型，我们的工作就完成了！

### **例 1:当前日期时间的整数时间戳**

在这里，我们导入日期时间模块以使用其中的日期时间函数。然后使用 datetime.now()函数获取当前日期和时间。使用 DateTime.timestamp()方法将 DateTime 对象转换为时间戳。我们将以秒为单位获取时间戳。然后舍入时间戳，并显式地将浮点数类型转换为整数，以秒为单位获得整数时间戳。

## 蟒蛇 3

```py
from datetime import datetime
curr_dt = datetime.now()

print("Current datetime: ", curr_dt)
timestamp = int(round(curr_dt.timestamp()))

print("Integer timestamp of current datetime: ",
      timestamp)
```

**输出:**

```py
Current datetime:  2021-08-25 15:04:33.794484
Integer timestamp of current datetime:  1629884074
```

### **例 2:指定日期时间的整数时间戳**

在 datetime()函数中给出日期和时间作为参数。使用 datetime.timestamp()方法将 datetime 对象转换为时间戳。我们将以秒为单位获取时间戳。舍入时间戳，并显式地将浮点数转换为整数，以秒为单位获取整数时间戳。我们还可以通过乘以 1000 将其转换为毫秒，以毫秒为单位获得整数时间戳。

## 蟒蛇 3

```py
from datetime import datetime
dtime = datetime(2018, 1, 1, 20)
print("Datetime: ", dtime)

dtimestamp = dtime.timestamp()
print("Integer timestamp in seconds: ",
      int(round(dtimestamp)))

milliseconds = int(round(dtimestamp * 1000))
print("Integer timestamp in milliseconds: ",
      milliseconds)
```

**输出:**

```py
Datetime:  2018-01-01 20:00:00
Integer timestamp in seconds:  1514817000
Integer timestamp in milliseconds:  1514817000000
```

### **示例 3:使用 calendar.timegm** 的 UTC(世界协调时)整数时间戳

首先，我们在 datetime.datetime()对象中输入 UTIC 时间。然后我们将对象传递给 d.timtuple()函数，该函数给出一个包含年、月、日等参数的 tuple，然后使用 calendar 函数将 datetime 转换为整数 UTC 时间戳。

## 蟒蛇 3

```py
import datetime
import calendar

d = datetime.datetime(1970, 1, 1, 2, 1, 0)
ttuple = d.timetuple()

itimestamp = calendar.timegm(ttuple)
print("Timestamp in integer since epoch:",
      itimestamp)
```

**输出:**

```py
Timestamp in integer since epoch: 7260
```

### **示例 4:特定时区整数时间戳**

首先，我们使用 datetime.datetime.now()获取当前时间。然后导入 pytz 库来实例化 timezone 对象以本地化日期时间。使用 datetime.timestamp()方法将 datetime 对象转换为时间戳。我们将以秒为单位获取时间戳。舍入并转换整数形式的时间戳以获得整数时间戳。

## 蟒蛇 3

```py
import datetime
import pytz

dtime = datetime.datetime.now()
timezone = pytz.timezone("Asia/Kolkata")
dtzone = timezone.localize(dtime)

print("Time Zone: ", dtzone.tzinfo)
print("Datetime: ", dtzone)

tstamp = dtzone.timestamp()
print("Integer timestamp: ", int(round(tstamp)))
```

**输出:**

```py
Time Zone:  Asia/Kolkata
Datetime:  2021-08-25 15:09:05.194413+05:30
Integer timestamp:  1629884345
```