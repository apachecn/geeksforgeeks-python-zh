# Python 日历模块:monthdays2calendar()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-monthdays 2 calendar-method/](https://www.geeksforgeeks.org/python-calendar-module-monthdays2calendar-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。
**monthdays 2 calendar()**Python 中的方法用于获取一年中某个月的周列表作为完整的周。

```
Syntax: monthdays2calendar(year, month)

Parameter: 
year: year of the calendar
month: month of the calendar

Returns: a list of the weeks in the month.
```

**代码#1:**

## 蟒蛇 3

```
# Python program to demonstrate working of
# monthdays2calendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

year = 2018
month = 9

# printing with monthdays2calendar
print(obj.monthdays2calendar(year, month))
```