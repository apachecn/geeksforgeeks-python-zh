# Python 日历模块| monthdayscalendar()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-monthdayscalendar-method/](https://www.geeksforgeeks.org/python-calendar-module-monthdayscalendar-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。
**monthdayscalendar()**Python 中的方法用于获取一年中某个月的周列表作为完整的周。

```
Syntax: monthdayscalendar(year, month)

Parameter: 
year: year of the calendar
month: month of the calendar

Returns: a list of the weeks in the month.
```

**代码#1:**

## 蟒蛇 3

```
# Python program to demonstrate working
# of monthdayscalendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

year = 2018
month = 9

# printing with monthdayscalendar
print(obj.monthdayscalendar(year, month))
```