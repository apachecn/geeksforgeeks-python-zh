# 如何在 Python 中把 DateTime 转换成整数

> 原文:[https://www . geesforgeks . org/如何在 python 中将日期时间转换为整数/](https://www.geeksforgeeks.org/how-to-convert-datetime-to-integer-in-python/)

Python 提供了一个名为 [DateTime](https://www.geeksforgeeks.org/python-datetime-module/) 的模块来执行所有与日期和时间相关的操作。它有一组丰富的函数，用来执行几乎所有与时间有关的操作。它需要先导入才能使用函数，并且它附带 python，所以不需要单独安装。

这里，我们处理一个特殊的日期对象。因此，要将给定日期转换为整数，我们可以遵循以下方法。

## **方法一:用 100 的乘法**

在这个方法中，我们将把日期的每个组成部分乘以 100 的倍数，并把它们全部相加，转换成整数。

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Getting todays date and time using now() of
# datetime class
current_date = datetime.datetime.now()

# Printing the current_date as the date object itself.
print("Original date and time object:", current_date)

# Retrieving each component of the date
# i.e year,month,day,hour,minute,second and
# Multiplying with multiples of 100
# year - 10000000000
# month - 100000000
# day - 1000000
# hour - 10000
# minute - 100
print("Date and Time in Integer Format:",
      current_date.year*10000000000 +
      current_date.month * 100000000 +
      current_date.day * 1000000 +
      current_date.hour*10000 +
      current_date.minute*100 +
      current_date.second)
```

**输出:**

```py
Original date and time object: 2021-08-10 15:51:25.695808
Date and Time in Integer Format: 20210810155125
```

## **方法二:使用 datetime.strftime()对象**

在这个方法中，我们使用 datetime 类的 strftime()函数，该函数将其转换为字符串，该字符串可以使用 int()函数转换为整数。

> **语法 ：** 时间（格式）
> 
> **返回:**返回日期或时间对象的字符串表示形式。

**代码:**

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Getting todays date and time using now() of datetime
# class
current_date = datetime.datetime.now()

# Printing the current_date as the date object itself.
print("Original date and time object:", current_date)

# Using the strftime() of datetime class
# which takes the components of date as parameter
# %Y - year
# %m - month
# %d - day
# %H - Hours
# %M - Minutes
# %S - Seconds
print("Date and Time in Integer Format:",
      int(current_date.strftime("%Y%m%d%H%M%S")))
```

**输出:**

```py
Original date and time object: 2021-08-10 15:55:19.738126
Date and Time in Integer Format: 20210810155519
```