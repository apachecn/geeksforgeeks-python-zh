# Python 日历模块:monthdatescalendar()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-monthdatescalendar-method/](https://www.geeksforgeeks.org/python-calendar-module-monthdatescalendar-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

**Python 中的 monthdatescalendar()** 方法用于获取一年中某个月的周列表作为完整周。

```py
Syntax: monthdatescalendar(year, month)

Parameter: 
year: year of the calendar
month: month of the calendar

Returns: a list of the weeks in the month.
```

**代码#1:**

## 蟒蛇 3

```py
# Python program to demonstrate working
# of monthdatescalendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

year = 2018
month = 9

# printing with monthdatescalendar
print(obj.monthdatescalendar(year, month))
```

**输出:**

> [[datetime.date（2018， 8， 27）， datetime.date（2018， 8， 28）， datetime.date（2018， 8， 29）， datetime.date（2018， 8， 30）， datetime.date（2018， 8， 31）， datetime.date（2018， 9， 1）， datetime.date（2018， 9， 2）]， [datetime.date（2018， 9， 3）， datetime.date（2018， 9， 4）， datetime.date（2018， 9， 5）， datetime.date（2018， 9， 9， 9， 9） [日期时间.日期（2018， 9， 10）， datetime.date（2018， 9， 11）， datetime.date（2018， 9， 12）， datetime.date（2018， 9， 13）， datetime.date（2018， 9， 14）， datetime.date（2018， 9， 15）， datetime.date（2018， 9， 16）]， [datetime.date（2018， 9， 17）， datetime.date（2018， 9， 18）， datetime.date（2018， 9， 19）， datetime.date（2018， 9， 20）， datetime.date（2018， 9， 21）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 23）] [datetime.date（2018， 9， 24）， datetime.date（2018， 9， 25）， datetime.date（2018， 9， 26）， datetime.date（2018， 9， 27）， datetime.date（2018， 9， 28）， datetime.date（2018， 9， 29）， datetime.date（2018， 9， 30）]]

请注意，输出中的周是七个 datetime.date 对象的列表。

**代码#2:** 迭代周列表

## 蟒蛇 3

```py
# Python program to demonstrate working
# of monthdatescalendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

# iterating with monthdatescalendar
for day in obj.monthdatescalendar(2018, 9):
    print(day)
```

**输出:**

> [datetime.date（2018， 8， 27）， datetime.date（2018， 8， 28）， datetime.date（2018， 8， 29）， datetime.date（2018， 8， 30）， datetime.date（2018， 8， 31）， datetime.date（2018， 9， 1）， datetime.date（2018， 9， 2）]
> [datetime.date（2018， 9， 3）， datetime.date（2018， 9， 4）， datetime.date（2018， 9， 5）， datetime.date（2018， 9， 6）， datetime.date（2018， 9， 7）， datetime.date（2018， 9， 8）， datetime.date（2018， 9， 9， 8）， datetime.date（2018， 9， 9， 9， 9）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9）， datetime.date（2018， 9， 9， 8）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9， 8）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9）， datetime.date（2018， 9， 9， 8）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9， 8）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9）， datetime.date（2018， 9， 9， 8）， datetime.date（2018， 9， 9， 6）， datetime.date（2018， 9， 9， 6）， datetime.date（2018， 9， 9， 6）， datetime.date（2018， 9， 7）， datetime.date（2018， 9， 9）， datetime.date（2018， 9， 9， 9）， datetime.date（2018， 9， 9， 6）， datetime.date（2018， 9， 8）， datetime.date（2018， 9， 9， 6）， datetime.date（ 9）]
> [日期时间.日期（2018， 9， 10）， datetime.date（2018， 9， 11）， datetime.date（2018， 9， 12）， datetime.date（2018， 9， 13）， datetime.date（2018， 9， 14）， datetime.date（2018， 9， 15）， datetime.date（2018， 9， 16）]
> [datetime.date（2018， 9， 17）， datetime.date（2018， 9， 18）， datetime.date（2018， 9， 1 datetime.date（2018， 9， 20）， datetime.date（2018， 9， 21）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 2018， 2018， 9， 20）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 2018， 9， 22）， datetime.date（2018， 9， 20）， datetime.date（2018， 9， 20）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 20， 20， 2018， 9， 20）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 20， 2018， 9， 20）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 22）， datetime.date（2018， 9， 2018， 9， 20）， datetime.date（2018， 9， 21）， datetime.date（201 9， 23）]
> [datetime.date（2018， 9， 24）， datetime.date（2018， 9， 25）， datetime.date（2018， 9， 26）， datetime.date（2018， 9， 27）， datetime.date（2018， 9， 28）， datetime.date（2018， 9， 29）， datetime.date（2018， 9， 30）]