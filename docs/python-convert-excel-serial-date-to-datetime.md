# Python–将 excel 序列日期转换为日期时间

> 原文:[https://www . geesforgeks . org/python-convert-excel-serial-date-datetime/](https://www.geeksforgeeks.org/python-convert-excel-serial-date-to-datetime/)

本文将讨论 Python 中 excel 序列日期到日期时间的转换。

Excel“序列日期”格式实际上是从 1900-01-00 开始的天数，即 1900 年 1 月 1 日。例如，excel 序列号 43831 代表 2020 年 1 月 1 日，在将 43831 转换为日期时间后，它将变成 2020-01-01。

通过使用**xlrd . xldate _ as _ datetime()**功能可以实现这一点。**xlrd . xldate _ as _ datetime()**函数用于将 excel 日期/时间数字转换为 datetime.datetime 对象。

> **语法:** xldate_as_datetime (xldate，datemode)
> 
> **参数:**该函数接受两个参数，如下图所示:
> 
> *   **xldate:** 这是将转换为日期时间的指定 excel 日期。
> *   **日期模式:**这是将执行转换的指定日期模式。
> 
> **返回值:**该函数返回 datetime.datetime 对象。

首先，调用 xlrd.xldate_as_datetime(date，0)函数将指定的 Excel 日期转换为 datetime.datetime 对象。然后，对返回的 datetime.datetime 对象调用 datetime.datetime.date()函数，将日期作为 datetime.date 对象返回。最后，调用 datetime.date.isoformat()函数将返回的 datetime.date 对象转换为 ISO 格式的日期字符串。

让我们看一些例子来说明上面的算法:

**示例:**将 excel 序列日期转换为字符串日期的 Python 程序

## 蟒蛇 3

```py
# Python3 code to illustrate the conversion
# of excel serial date to datetime

# Importing xlrd module
import xlrd

# Initializing an excel serial date
xl_date = 43831

# Calling the xldate_as_datetime() function to
# convert the specified excel serial date into
# datetime.datetime object
datetime_date = xlrd.xldate_as_datetime(xl_date, 0)

# Calling the datetime_date.date() function to convert
# the above returned datetime.datetime object into
# datetime.date object
date_object = datetime_date.date()

# Calling the isoformat() function to convert the
# above returned datetime.date object into the
# ISO format date string
string_date = date_object.isoformat()

# Getting the converted date string as output
print(string_date)

# Getting the type of returned date format
print(type(string_date))
```

**输出:**

```py
2020-01-01
<class 'str'>
```

**示例 2:** 将 excel 序列号转换为 DateTime 的 Python 程序

## 蟒蛇 3

```py
# Python3 code to illustrate the conversion
# of excel serial date to datetime

# Importing xlrd module
import xlrd

# Initializing an excel serial date
xl_date = 43831

# Calling the xldate_as_datetime() function to
# convert the specified excel serial date into
# datetime.datetime object
datetime_date = xlrd.xldate_as_datetime(xl_date, 0)

# Calling the datetime_date.date() function to convert
# the above returned datetime.datetime object into
# datetime.date object
date_object = datetime_date.date()

# Getting the converted date date as output
print(date_object)

# Getting the type of returned date format
print(type(date_object))
```

**输出:**

```py
2020-01-01
<class 'datetime.date'>
```