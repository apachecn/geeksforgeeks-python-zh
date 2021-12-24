# Python 中 Datetime.date 类的 isocalendar()函数

> 原文:[https://www . geesforgeks . org/isocalendar-日期时间函数-日期类-在 python 中/](https://www.geeksforgeeks.org/isocalendar-function-of-datetime-date-class-in-python/)

**isocalendar()** 函数用于返回包含 ISO 年、ISO 周数和 ISO 工作日的元组。

**注:**

*   根据 ISO 标准 8601 和 ISO 标准 2015，星期四是一周的中间一天。
*   因此，ISO 年总是从周一开始。
*   ISO 年可以有 52 个完整周，也可以有 53 个完整周。
*   ISO 年在年初或年末没有任何分数周。

> **语法:** isocalendar()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回 ISO 年、ISO 周数和 ISO 工作日的元组。

**例 1:** 获取 ISO 年、ISO 周数、ISO 工作日。

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

**例 2:** 获取 ISO 年份、ISO 周数、ISO 工作日和特定日期。

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