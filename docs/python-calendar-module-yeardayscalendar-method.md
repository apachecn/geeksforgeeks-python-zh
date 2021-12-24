# Python 日历模块:yeardayscalendar()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-yeardayscalendar-method/](https://www.geeksforgeeks.org/python-calendar-module-yeardayscalendar-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

**使用 Python 中的 yeardayscalendar()** 方法获取指定年份的数据。周列表中的条目是日数。本月以外的天数为零。

```
Syntax: yeardayscalendar(year, width)

Parameter: 
year: year of the calendar
width: *[Default: 3]* number of months in each row. 

Returns: list of day numbers.
```

**代码#1:**

## 蟒蛇 3

```
# Python program to demonstrate working
# of yeardayscalendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

year = 2016
# default value of width is 3

# printing with yeardayscalendar
print(obj.yeardayscalendar(year))
```

**输出:**

> [[[[0，0，0，0，1，2，3]，[4，5，6，7，8，9，10]，[11，12，13，14，15，16，17]，[18，19，20，21，22，23，24]，[25，26，27，28，29，30，31]，[[1，2，3，4，5，6，7]……
> …]

**代码#2:** 迭代周列表

## 蟒蛇 3

```
# Python program to demonstrate working
# of yeardayscalendar() method

# importing calendar module
import calendar

obj = calendar.Calendar()

# iterating with yeardayscalendar
for day in obj.yeardayscalendar(2018, 1):
    print(day)
```

**输出:**

> [[[1，2，3，4，5，6，7]，[8，9，10，11，12，13，14]，[15，16，17，18，19，20，21]，[22，23，24，25，26，27，28]，[29，30，31，0，0，0，0，]]
> [[0，0，0，1，2，3，4]，[T0 [3, 4, 5, 6, 7, 8, 9], [10, 11, 12, 13, 14, 15, 16], [17, 18, 19, 20, 21, 22, 23], [24, 25, 26, 27, 28, 29, 30], [31, 0, 0, 0, 0, 0, 0]]]