# Python 日历模块:yeardays2calendar()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-year days 2 calendar-method/](https://www.geeksforgeeks.org/python-calendar-module-yeardays2calendar-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。
**year days 2 calendar()**Python 中的方法用于获取指定年份的数据。周列表中的条目是天数和工作日数的元组。本月以外的天数为零。

```
Syntax: yeardays2calendar(year, width)

Parameter: 
year: year of the calendar
width: *[Default: 3]* number of months in each row. 

Returns: tuples of day numbers and weekday numbers.
```

**代码#1:**

## 蟒蛇 3

```
# Python program to demonstrate working
# of yeardays2calendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

year = 2016
# default value of width is 3

# printing with yeardays2calendar
print(obj.yeardays2calendar(year))
```