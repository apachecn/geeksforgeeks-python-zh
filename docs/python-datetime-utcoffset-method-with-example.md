# Python datetime.utcoffset()方法示例

> 原文:[https://www . geeksforgeeks . org/python-datetime-utc offset-method-with-example/](https://www.geeksforgeeks.org/python-datetime-utcoffset-method-with-example/)

**utcoffset()** 函数用于返回一个 timedelta 对象，该对象表示本地时间和 UTC 时间之间的差异。

*   此函数用在模块 datetime 的 datetime 类中。
*   这里 utcoffset 的范围是“时间增量(小时=24) <= offset <=时间增量(小时=24)”。
*   如果偏移量在世界协调时以东，则认为是正的；如果偏移量在世界协调时以西，则认为是负的。因为一天有 24 个小时，-timedelta(24)和 timedelta(24)是可能的最大值。

> **语法:** utcoffset()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回一个 timedelta 对象，表示本地时间和 UTC 时间之间的差值。

**示例 1:** 这里的输出是 none，因为 now()函数以 UTC 格式返回日期和时间，因此本地时间(即 now()函数返回的时间)和 UTC 时间之间的差异是 None。

## 蟒蛇 3

```
# Python3 code for getting
# the difference between the
# local time and UTC time

# Importing datetime and pytz module
from datetime import datetime
import pytz

# Calling the now() function to get
# current date and time
date_time = datetime.now()

# Calling the utcoffset() function
# over the above intitialized datetime
print(date_time.utcoffset())
```

**输出:**

> 没有人

**例 2:** 求时间偏移

## 蟒蛇 3

```
# Python3 code for getting
# the difference between the
# local time and UTC time

# Importing datetime and pytz module
from datetime import datetime
import pytz

# Calling the now() function to
# get current date and time
naive = datetime.now()

# adding a timezone
timezone = pytz.timezone("Asia/Kolkata")
aware1 = timezone.localize(naive)

# Calling the utcoffset() function
# over the above localized time
print("Time ahead of UTC by:", aware1.utcoffset())
```

**输出:**

> 世界协调时提前 5:30:00

**示例 3:** 查找时间偏移

## 蟒蛇 3

```
# Python3 code for getting
# the difference between the
# local time and UTC time

# Importing datetime and pytz module
from datetime import datetime
import pytz

# Calling the now() function to
# get current date and time
naive = datetime.now()

# adding a timezone
timezone = pytz.timezone("Asia/Tokyo")
aware1 = timezone.localize(naive)

# Calling the utcoffset() function
# over the above localized time
print("Time ahead of UTC by:", aware1.utcoffset())
```

**输出:**

> 时间比世界协调时提前:9:00:00