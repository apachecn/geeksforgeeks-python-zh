# 日期时间的等格式–Python

> 原文:[https://www.geeksforgeeks.org/isoformat-to-datetime-python/](https://www.geeksforgeeks.org/isoformat-to-datetime-python/)

在本文中，我们将看到如何在 Python 中将 Isoformat 转换为 datetime。

## **方法 1:** 在日期时间模块中使用 fromisoformat()

在这个方法中，我们将使用 fromisoformat()将字符串转换为 DateTime 对象。

**语法:**

> datetime . fromisoformatc(日期)

**示例:**将异格式转换为日期时间

## 蟒蛇 3

```py
# importing datetime module
from datetime import datetime

# Getting today's date
todays_Date = datetime.now()

# Get date into the isoformat
isoformat_date = todays_Date.isoformat()

# print the type of date
print(type(isoformat_date))

# convert string date into datetime format
result = datetime.fromisoformat(isoformat_date)
print(type(result))
```

**输出:**

```py
<class 'str'>
<class 'datetime.datetime'>
```

## **方法 2:** 在 dateutil 模块中使用 parse()

在这个方法中，我们将使用这个内置的 Python 库 python-dateutil，parse()方法可以用来检测字符串中的日期和时间。

> **语法:**date util . parser . parse((isoformat _ string)
> 
> **参数:** Isoformat_string: Str。
> 
> **返回:** Datetime 对象

**示例:**将异格式转换为日期时间

## 蟒蛇 3

```py
# importing datetime module
from datetime import datetime
import dateutil

# Getting today's date
todays_Date = datetime.now()
isoformat_date = todays_Date.isoformat()

# display isoformat type
print(type(isoformat_date))

# convert it into datetime and display
result = dateutil.parser.parse(isoformat_date)
print(type(result))
```

**输出:**

```py
<class 'str'>
<class 'datetime.datetime'>
```