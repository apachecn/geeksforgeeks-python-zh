# Python–datetime . to ordinal()方法，示例

> 原文:[https://www . geesforgeks . org/python-datetime-toordinal-method-with-example/](https://www.geeksforgeeks.org/python-datetime-toordinal-method-with-example/)

**datetime.toordinal()** 是一个用于操作 datetime 类对象的简单方法。它返回日期的公历序数，其中第 1 年的 1 月 1 日具有序数 1。该函数返回给定日期时间对象的序号值。

如果第 1 年的 1 月 1 日有序数 1，那么第 1 年的 1 月 2 日将有序数 2，以此类推。

> **语法:**
> 
> datetimeObj.toordinal()
> 
> **参数:**无
> 
> **返回:**序数

下面给出了相同的一些实现。

**示例 1:** 使用日期时间模块的 date.today()类，使用 *datetime.toordinal()* 函数返回给定日期时间对象的公历序数。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Getting Ordinal value using
# toordinal().

# importing datetime module for today()
import datetime

# using date.today() to get todays date
dateToday = datetime.date.today()

# Using toordinal() to generate ordinal value.
toOrdinal = dateToday.toordinal()

# Prints Ordinal Value of Todays Date.
print(f"Ordinal of date {dateToday} is {toOrdinal}")
```

**Output**

```py
Ordinal of date 2021-08-03 is 738005
```

**注意:**日期时间类的属性应该在给定的范围内，否则会显示**值错误**

**示例 2:** 显示参数的示例需要在范围内

## 蟒蛇 3

```py
# importing datetime class
from datetime import datetime

# Creating an instance of datetime.
dateIs = datetime(189, 0, 0)

# Using toordinal() method
toOrdinal = dateIs.toordinal()
print(f"Ordinal value of Earliest Datetime {dateIs} is {toOrdinal}")
```

**输出:**

> 追溯(最近一次通话持续时间):
> 
> 文件"/home/2 ecd5f 27 FBC 894 dc8 eab 3a a 6559 c7ab . py "，第 5 行，在
> 
> 文件=日期时间(189，0，0)
> 
> 值错误:月份必须在 1 中..12

**示例 3:** 使用 datetime.toordinal()函数返回给定 datetime 对象的公历序数。

## 蟒蛇 3

```py
# importing datetime class
from datetime import datetime

# Creating an instance of datetime.
dateIs = datetime(1, 1, 1, 0, 0, 0, 0)

# Using toordinal() method
toOrdinal = dateIs.toordinal()
print(f"Ordinal value of Earliest Datetime {dateIs} is {toOrdinal}")

print()

dateIs = datetime(9999, 12, 31, 23, 59, 59)
toOrdinal = dateIs.toordinal()
print(f"Ordinal value of Latemost Datetime {dateIs} is {toOrdinal}")
```

**输出:**

> 最早日期时间 0001-01-01 00:00:00 的序号值为 1
> 
> 最近日期时间 9999-12-31 23:59:59 的序号值是 3652059