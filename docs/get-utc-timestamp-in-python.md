# 获取 Python 中的 UTC 时间戳

> 原文:[https://www.geeksforgeeks.org/get-utc-timestamp-in-python/](https://www.geeksforgeeks.org/get-utc-timestamp-in-python/)

[Datetime](https://www.geeksforgeeks.org/python-datetime-module-with-examples/) 模块提供了处理日期和时间的类。这些类提供了许多函数来处理日期、时间和时间间隔。日期和日期时间在 Python 中是一个对象，所以当您操作它们时，您实际上是在操作对象，而不是字符串或时间戳。

**注意:**更多信息请参考 [Python 日期时间模块，示例](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

**示例:**

```
# Python program to demonstrate
#  datetime module

import datetime

dt = datetime.date(2020, 1, 26)
# prints the date as date
# object
print(dt)

# prints the current date
print(datetime.date.today())

# prints the date and time
dt = datetime.datetime(1999, 12, 12, 12, 12, 12, 342380) 
print(dt)

# prints the current date 
# and time
print(datetime.datetime.now())
```

**输出:**

```
2020-01-26
2020-02-04
1999-12-12 12:12:12.342380
2020-02-04 07:46:29.315237

```

#### 获取世界协调时时间戳

使用`datetime.datetime.now()`获取当前日期和时间。然后使用`tzinfo`类将我们的日期时间转换为世界协调时。最后，使用`timestamp()`转换日期时间对象，以世界协调时为单位，得到世界协调时时间戳。

**示例:**

```
from datetime import timezone
import datetime

# Getting the current date
# and time
dt = datetime.datetime.now(timezone.utc)

utc_time = dt.replace(tzinfo=timezone.utc)
utc_timestamp = utc_time.timestamp()

print(utc_timestamp)
```

**输出:**

```
1615975803.787904

```