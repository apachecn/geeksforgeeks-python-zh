# Python 中日期时间类的 Isocalendar()方法

> 原文:[https://www . geesforgeks . org/isocalendar-method-of-datetime-in-class-python/](https://www.geeksforgeeks.org/isocalendar-method-of-datetime-class-in-python/)

**isocalendar()** 函数用于返回 ISO 年、ISO 周数和 ISO 工作日的元组。

**注:**

*   根据 ISO 标准 8601 和 ISO 标准 2015，星期四是一周的中间一天。
*   因此，ISO 年总是从周一开始。
*   国际标准化组织的年份可以从每年的 1 月 29 日开始，也可以从公历的 1 月 4 日开始。
*   ISO 年可以有 52 个完整周，也可以有 53 个完整周。
*   ISO 年在年初或年末没有任何分数周。

> **语法:** isocalendar()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回 ISO 年、ISO 周数和 ISO 工作日的元组。

**示例 1:** 使用今天的日期。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting a tuple of ISO Year,
# ISO Week Number and ISO Weekday

# Importing date module from datetime
from datetime import date

# Calling the today() function
# to return todays date
Todays_date = date.today()

# Printing today's date
print(Todays_date)

# Calling the isocalendar() function
# over the above today's date to return
# its ISO Year, ISO Week Number
# and ISO Weekday
print(Todays_date.isocalendar())
```

**输出:**

```
2021-07-25
(2021, 29, 7)
```

**示例 2:** 使用特定日期。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting a tuple of ISO Year,
# ISO Week Number and ISO Weekday

# Importing date module from datetime
from datetime import date

# Creating an instance for
# different dates
A = date(2020, 10, 11)

# Calling the isocalendar() function
# over the above specified date
Date = A.isocalendar()

# Printing Original date and its
# ISO Year, ISO Week Number
# and ISO Weekday
print("Original date:",A)
print("Date in isocalendar is:", Date)
```

**输出:**

```
Original date: 2020-10-11
Date in isocalendar is: (2020, 41, 7)
```