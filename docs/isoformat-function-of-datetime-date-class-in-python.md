# Python 中 Datetime.date 类的 Isoformat()函数

> 原文:[https://www . geesforgeks . org/isoformat-function-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/isoformat-function-of-datetime-date-class-in-python/)

**Isoformat()** 函数用于返回日期、时间和 UTC 偏移的字符串到 **ISO 8601** 格式的相应时区。

标准的 ISO 8601 格式是关于公历的日期格式。这种格式规定，日历日期需要用 4 位数字的年份、两位数字的月份和两位数字的日期来表示。即 YYYY-MM-DD。例:2020-01-01。

> **语法:**等值格式(sep =‘t’，time pec =‘auto’)
> 
> **参数:**该函数接受两个参数，如下图所示:
> 
> *   **sep:** 是日期和时间字段之间要打印的分隔符。它是一个可选参数，默认值为“T”。
> *   **timespec:** 是 timespec 的格式说明符。它也是一个可选参数，默认值为“自动”。
> 
> **返回值:**该函数以 **ISO 8601** 格式返回 Python DateTime.date 对象的日期值。

**示例 1:** 在下面的示例中，isoformat()函数在今天的日期被调用，它以 ISO 8601 格式返回相同的今天的日期字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting date values in ISO 8601 format

# importing datetime and time module
import datetime
import time

# Getting today's date
todays_Date = datetime.date.fromtimestamp(time.time());

# Calling the isoformat() function over the
# today's date
date_in_ISOFormat = todays_Date.isoformat();

# Printing Today's date in ISO format
print("Today's date in ISO Format: %s"%date_in_ISOFormat);
```

**输出:**

```
Today's date in ISO Format: 2021-07-27
```

**示例 2:** 在下面的示例中，isoformat()函数在今天的日期和时间被调用，它以 ISO 8601 格式返回相同的今天的日期和时间字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting date and time values
# in ISO 8601 format

# importing datetime and time module
import datetime
import time

# Getting today's date and time
todays_Date = datetime.datetime.now();

# Calling the isoformat() function over the
# today's date and time
DateTime_in_ISOFormat = todays_Date.isoformat();

# Printing Today's date and time in ISO format
print("Today's date and time in ISO Format: %s"%DateTime_in_ISOFormat);
```

**输出:**

> ISO 格式的今天的日期和时间:2021-07-27T16:02:08.070557

**示例 3:** 在下面的示例中，isoformat()函数采用了两个参数，一个是分隔符字符，如“#”，另一个参数是特定于时间的格式说明符。这里使用了特定于时间的参数的不同值，这些值已经在上面的参数部分进行了说明。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting date and time values
# in ISO 8601 format

# importing datetime module
import datetime

# Getting today's date and time
DateTime_in_ISOFormat = datetime.datetime.now();

# Printing Today's date and time in ISO format of
# auto value for the format specifier
print(DateTime_in_ISOFormat.isoformat("#", "auto"))

# Printing Today's date and
# time format specifier as hours
print(DateTime_in_ISOFormat.isoformat("#", "hours"))

# Printing Today's date and
# time format specifier as minutes
print(DateTime_in_ISOFormat.isoformat("#", "minutes"))

# Printing Today's date and time
# format specifier as seconds
print(DateTime_in_ISOFormat.isoformat("#", "seconds"))

# Printing Today's date and time
# format specifier as milliseconds
print(DateTime_in_ISOFormat.isoformat("#", "milliseconds"))

# Printing Today's date and time
# format specifier as microseconds
print(DateTime_in_ISOFormat.isoformat("#", "microseconds"))
```

**输出:**

```
2021-07-27#16:01:12.090202
2021-07-27#16
2021-07-27#16:01
2021-07-27#16:01:12
2021-07-27#16:01:12.090
2021-07-27#16:01:12.090202
```