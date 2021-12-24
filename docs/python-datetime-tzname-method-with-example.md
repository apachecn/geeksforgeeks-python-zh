# Python datetime.tzname()方法示例

> 原文:[https://www . geesforgeks . org/python-datetime-tzname-method-with-example/](https://www.geeksforgeeks.org/python-datetime-tzname-method-with-example/)

**tzname()** 方法用于模块 DateTime 的 DateTime 类。此方法用于以字符串形式返回传递的日期时间对象的时区名称。

**语法:**

> tzname()

**返回类型:**

它将以字符串形式返回传递的 DateTime 对象的时区名称。

所以首先我们需要导入模块 DateTime，为了得到确切位置的时区，我们将简单地把 [datetime.now()](https://www.geeksforgeeks.org/python-now-function/) 函数生成的 DateTime 戳传递给 tzname()函数。

**示例 1:** Python 程序，将返回无的 tzinfo()

## 蟒蛇 3

```py
# import datetime module
from datetime import datetime

# import pytz module
import pytz

# get the datetime of the present
dt = datetime.now()

# Tzinfo is missing from the time object
print(dt)

# display tz info for the dt
print(dt.tzinfo)
print("Timezone:", dt.tzname())
print()
```

**输出:**

> 2021-08-06 02:58:15.162869
> 
> 没有人
> 
> 时区:无

也可以通过显式添加时区来获取其他地方的时区。

**示例 2:** Python 程序添加亚洲/加尔各答的时区并获取时区详细信息

## 蟒蛇 3

```py
# import datetime module
from datetime import datetime

# import pytz module
import pytz

# get the datetime of the present
dt = datetime.now()

# Tzinfo is missing from the time object
print(dt)

# display tz info for the dt
print(dt.tzinfo)
print("Timezone:", dt.tzname())
print()

# Adding a timezone for asia /kolkate
timezone = pytz.timezone("Asia/Kolkata")

# getting the timezone using localize method
mydt = timezone.localize(dt)

print(mydt)

# getting the time zone info using tzinfo method
print("Tzinfo:", mydt.tzinfo)

# display time zone name using tzname
print("Timezone name:", mydt.tzname())
```

**输出:**

> 2021-08-06 03:00:44.949286
> 
> 没有人
> 
> 时区:无
> 
> 2021-08-06 03:00:44.949286+05:30
> 
> Tzinfo:亚洲/加尔各答
> 
> Timezone name:是

**示例 3:** 获取亚洲/东京的时区详细信息

## 蟒蛇 3

```py
# import datetime module
from datetime import datetime

# import pytz module
import pytz

# get the datetime of the present
dt = datetime.now()

# Tzinfo is missing from the time object
print(dt)

# display tz info for the dt
print(dt.tzinfo)
print("Timezone:", dt.tzname())
print()

# Adding a timezone for asia /Tokyo
timezone = pytz.timezone("Asia/Tokyo")

# getting the timezone using localize method
mydt = timezone.localize(dt)

print(mydt)

# getting the time zone info using tzinfo method
print("Tzinfo:", mydt.tzinfo)

# display time zone name using tzname
print("Timezone name:", mydt.tzname())
```

**输出:**

> 2021-08-06 03:02:02.569770
> 
> 没有人
> 
> 时区:无
> 
> 2021-08-06 03:02:02.569770+09:00
> 
> Tzinfo:亚洲/东京
> 
> 时区名称:JST