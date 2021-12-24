# Python 日历模块:yeardatescalendar()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-year datescalendar-method/](https://www.geeksforgeeks.org/python-calendar-module-yeardatescalendar-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。
**Python 中的 yeardatescalendar()** 方法用于获取一年中某个月的周列表作为完整的周。周列表中的条目是日数。本月以外的天数为零。

```py
Syntax: yeardatescalendar(year, width)

Parameter: 
year: year of the calendar
width: *[Default: 3]* number of months in each row. 

Returns: a list of month rows.
```

**代码#1:**

## 蟒蛇 3

```py
# Python program to demonstrate working
# of yeardatescalendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

year = 2016
# default value of width is 3

# printing with yeardatescalendar
print(obj.yeardatescalendar(year))
```