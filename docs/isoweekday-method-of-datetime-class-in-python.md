# Python 中日期时间类的等周()方法

> 原文:[https://www . geesforgeks . org/iso weekday-of-datetime-in-class-python/](https://www.geeksforgeeks.org/isoweekday-method-of-datetime-class-in-python/)

**Isoweekday()** 是 DateTime 类的一个方法，它告诉给定日期的一天。它返回一个对应于特定日期的整数。

> **语法：** datetime.isoweekday（）
> 
> **参数:**无
> 
> **返回值:**根据表返回一个对应于一天的整数

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

**例 1:** 打印当前日期的当天。

## 蟒蛇 3

```
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the
# week using the return value of the
# isoweekday() function
weekdays = {1: "Monday",
            2: "Tuesday",
            3: "Wednesday",
            4: "Thursday",
            5: "Friday",
            6: "Saturday",
            7: "Sunday"}

# Getting current date using today()
# function of the datetime class
todays_date = datetime.date.today()
print("Today's date is :", todays_date)

# Using the isoweekday() function to
# retrieve the day of the given date
day = todays_date.isoweekday()
print("The date", todays_date, "falls on",
      weekdays[day])
```

**输出:**

```
Today's date is : 2021-07-27
The date 2021-07-27 falls on Tuesday
```

**例 2:** 获取 2010 年至今的今天的星期几

## 蟒蛇 3

```
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the
# week using the return value of the
# isoweekday() function
weekdays = {1: "Monday",
            2: "Tuesday",
            3: "Wednesday",
            4: "Thursday",
            5: "Friday",
            6: "Saturday",
            7: "Sunday"}

# Getting current year using today() function
# of the datetime class and the year attribute
Today = datetime.date.today()
current_year = Today.year

for i in range(2010, current_year+1):
    # Printing the day of the year
    # by first creating an datetime object
    # for the starting day of the year and
    # then we use isoweekday
    # to get the value and we use the
    # weekdays to retrieve the day of the year
    print("The {}/{} in the year {} has fallen on {}".\
          format(Today.month, Today.day, i,
          weekdays[datetime.date(i, Today.month,
                    Today.day).isoweekday()]))
```

**输出:**

> 2010 年的 7/28 已经在周三落下帷幕
> 
> 2011 年的 7/28 已经在周四落下
> 
> 2012 年的 7/28 发生在周六
> 
> 2013 年的 7/28 发生在周日
> 
> 2014 年的 7/28 已经在周一落下帷幕
> 
> 2015 年的 7/28 已经在周二落下
> 
> 2016 年的 7/28 已经在周四落下
> 
> 2017 年的 7/28 已经在周五落下
> 
> 2018 年的 7/28 已经在周六落下帷幕
> 
> 2019 年的 7/28 发生在周日
> 
> 2020 年的 7/28 已经在周二落下
> 
> 2021 年的 7/28 已经在周三落下帷幕