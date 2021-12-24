# Python 日历模块| itermonthdays2()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-itermonthdays 2-method/](https://www.geeksforgeeks.org/python-calendar-module-itermonthdays2-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

**`itermonthdays2()`** 方法用于获取一年中月份的迭代器，类似于`itermonthdates()`。返回的天数将只是每月的天数。对于指定月份之外的天数，天数为 0。

> **语法:** itermonthdays2(年、月)
> 
> **参数:**T2**年:**年的日历
> 月:月的日历
> 
> **返回:**当月的迭代器。

**代码# 1:**itermonthdays 2()方法的工作示例

```py
# Python program to demonstrate working
# of itermonthdates() method

# importing calendar module
import calendar

obj = calendar.Calendar()

# iterating with itermonthdays2
for day in obj.itermonthdays2(2018, 9):
    print(day)
```

**输出:**

```py
The starting day number in calendar is : 0
(0, 0)
(0, 1)
(0, 2)
(0, 3)
(0, 4)
(1, 5)
(2, 6)
(3, 0)
.
.
(29, 5)
(30, 6)
```

**代码# 2:**itermonthdays 2()方法的工作示例，firstweekday=2

```py
# Python program to demonstrate working
# of itermonthdates() method

# importing calendar module
import calendar

obj = calendar.Calendar(firstweekday = 2)

# iterating with parameter itermonthdays2
for day in obj.itermonthdays2(2018, 9):
    print(day)
```

**输出:**

```py
(0, 2)
(0, 3)
(0, 4)
(1, 5)
(2, 6)
(3, 0)
(4, 1)
.
.
(27, 3)
(28, 4)
(29, 5)
(30, 6)
(0, 0)
(0, 1)
```