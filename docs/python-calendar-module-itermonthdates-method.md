# Python 日历模块| itermonthdates()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-itermonthdates-method/](https://www.geeksforgeeks.org/python-calendar-module-itermonthdates-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。
**itermonthdates()** 方法返回一年中月份(1–12)的迭代器。这个迭代器将返回一个月中的所有日子，以及在一个月开始之前或结束之后获得完整一周所需的所有日子。

```py
Syntax: itermonthdates(year, month)

Parameter: 
year: year of the calendar
month: month of the calendar

Returns: an iterator for the month.
```

**代码#1:**

## 蟒蛇 3

```py
# Python program to demonstrate working
# of itermonthdates() method

# importing calendar module
from calendar import Calendar

obj = calendar.Calendar()

# iterating with itermonthdates
for day in obj.itermonthdates(2018, 9):
    print(day)
```