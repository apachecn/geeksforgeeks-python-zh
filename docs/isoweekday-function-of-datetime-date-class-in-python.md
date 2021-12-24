# Python 中 Datetime.date 类的 Isoweekday()函数

> 原文:[https://www . geesforgeks . org/iso weekday-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/isoweekday-function-of-datetime-date-class-in-python/)

**isoweekday()** 是一个返回一个整数的函数，该整数告诉给定的日期。根据下表，它返回的整数代表一天。

> **语法：** datetime.isoweekday（）
> 
> **返回值:**范围为[1，7]的整数

<figure class="table">

| 返回的整数 | 一周中的某一天 |
| --- | --- |
| one | 星期一 |
| Two | 星期二 |
| three | 星期三 |
| four | 星期四 |
| five | 星期五 |
| six | 星期六 |
| seven | 星期日 |

</figure>

**示例 1:** 这个程序使用 DateTime 模块抓取日期，并告诉日期的日期。

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Creating an list which will
# be  used to retrieve the day of the
# week using the return value of the
# isoweekday() function
DaysList  = ["None",
              "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday",
            "Sunday"]

# Using the function today()
# to get today's date
CurrentDate = datetime.date.today()
print("Current Date is :", CurrentDate)

# Using the isoweekday() function to
# retrieve the day of the given date
day = CurrentDate.isoweekday()
print("The date", CurrentDate, "falls on",
      DaysList[day])
```

**输出:**

```py
Current Date is : 2021-08-18
The date 2021-08-18 falls on Wednesday
```

**示例 2:** 在本例中，我们将接受用户输入的日期，并将返回它的日期。

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the week
# using the return value of the isoweekday()
# function
DaysList = ["None",
            "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday",
            "Sunday"]

# Getting the  user's input
day = 18
month = 9
year = 2020

# Creating the datetime object for the user's
# input by using the date() function of datetime
# class
Date = datetime.date(year, month, day)

# Using the isoweekday() function
# to retrieve the day of the given date
day = Date.isoweekday()

print("The given date", Date, "falls on",
      DaysList[day])
```

**输出:**

```py
The given date 2020-09-18 falls on Friday
```

**示例 3:** 在本例中，我们将获取用户输入的日期和日期，如果是真的，则返回

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the week
# using the return value of the isoweekday()
# function
DaysList = ["None",
            "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday",
            "Sunday"]

# Getting the  user's input
day = 1
month = 1
year = 2021
day_fallen = "Friday"

# Creating the datetime object for the user's
# input by using the date() function of datetime
# class
Date = datetime.date(year, month, day)

# Using the isoweekday() function
# to retrieve the day of the given date
day = Date.isoweekday()

# Checking if the day is matching the user's
# day
if day_fallen.lower() == DaysList[day].lower():
    print("Yes, your given date", Date,
          "falls on your expected day i.e ",
          DaysList[day])
else:
    print("No, your given date", Date, "falls on",
          DaysList[day],
          "but not on", day_fallen)
```

**输出:**

> 是的，你给定的日期 2021-01-01 正好是你的预计日期，也就是星期五