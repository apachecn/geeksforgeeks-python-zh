# Python DateTime astimezone()方法

> 原文:[https://www . geesforgeks . org/python-datetime-astimezone-method/](https://www.geeksforgeeks.org/python-datetime-astimezone-method/)

**astimezone()** 函数用于根据指定的时区参数 tz 返回一个 DateTime 实例。

**注意:**根据 tz 参数，返回的 DateTime 实例具有新的 UTC 偏移值。如果这个函数没有参数 tz，那么返回的 DateTime 对象将具有本地日期、时间和时区。

> **语法:**像散区(tz =无)
> 
> **参数:**该函数接受一个可选参数，如下图所示:
> 
> *   **tz:** 这是指定的时区。
> 
> **返回值:**该函数根据指定的时区参数 tz 返回一个 datetime 实例。如果未指定参数 tz，则该函数返回本地日期、时间和时区。

**例 1:** 在下面的例子中，astimezone()函数是以新加坡时区对象为参数的。Singapore timedelta()函数以 5 小时为参数，其返回值作为 timezone()函数的参数。这样，为函数 astimezone()初始化了一个 datetime 和新加坡时区对象，以返回其对应的 DateTime 实例。

## 蟒蛇 3

```
# Python3 code for getting
# a datetime instance according
# to the specified time zone parameter tz

# Importing datetime module
import datetime

# Specifying Singapore timedelta and timezone
# object
sgtTimeDelta = datetime.timedelta(hours=5)
sgtTZObject = datetime.timezone(sgtTimeDelta,
                                name="SGT")

# Specifying a datetime along with Singapore
# timezone object
d1 = datetime.datetime(2021, 8, 4, 10,
                       00, 00, 00, sgtTZObject)

# Calling the astimezone() function over the above
# specified Singapore timezone
d2 = d1.astimezone(sgtTZObject)

# Printing a datetime instance as per the above
# specified Singapore timezone
print("Singapore time from a datetime instance:{}".format(d2))
```

**输出:**

> 日期时间实例的新加坡时间:2021-08-04 10:00:00+05:00

**示例 2:** 在下面的示例中，astimezone()函数不接受任何参数，因此该函数返回具有本地当前日期、时间和时区的 DateTime 对象。在这里，由于 datetime.now()函数，返回了当前日期、时间和时区。

## 蟒蛇 3

```
# Python3 code for getting
# a datetime instance according
# to the specified time zone parameter tz

# Importing datetime module
import datetime

# Calling now() function to return
# current datetime
d1 = datetime.datetime.now()

# Calling the astimezone() function without
# any timezone parameter
d2 = d1.astimezone()

# Printing the local current date, time and
# timezone
print(format(d2))
```

**输出:**

```
2021-08-04 06:41:15.128046+00:00
```