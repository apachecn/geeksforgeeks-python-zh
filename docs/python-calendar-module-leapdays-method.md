# Python 日历模块:leapdays()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-leap days-method/](https://www.geeksforgeeks.org/python-calendar-module-leapdays-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

在 Python 中， **`calendar.leapdays()`** 是日历模块中为简单文本日历提供的功能。

**`leapdays()`** 法用于**获取指定年份范围内的闰年数。**

```
Syntax: leapdays()
Parameter: 
year1, year2:  years to get the number of leap years.

Returns: Returns number of leap years in a specified range.
```

**代码#1:**

```
# Python program to explain working of leapdays() method

# importing calendar module
import calendar

# checking number of leap years in range
print(calendar.leapdays(2016, 2022))
print(calendar.leapdays(2001, 2003))
```

**输出:**

```
2
0
```

**代码#2:** 解释`leapdays()`方法的工作。

下面的代码打印闰年数和上一个闰年的第一个月日历(如果在给定范围内找到任何闰年)，否则通知没有年份是闰年。

```
# Python code to demonstrate the working of leapdays() 

# importing calendar module for calendar operations 
import calendar 

year1 = 2005
year2 = 2025

# calling leapdays() method to verify
val = str(calendar.leapdays(year1, year2))
print("Number of leap years found is % s" % val)

count = 0
# checking the condition is True or not
for year in range(year1, year2):
    val = calendar.isleap(year)
    if val == True:
        lyear = year
        count += 1

if count >= 1:

    # print 1th month of first leap year 
    calendar.prmonth(lyear, 1, 2, 1) 

# Returned False, year is not a leap
else:
    print("No leap year found")
```

**输出:**

```
Number of leap years found is 5
    January 2024
Mo Tu We Th Fr Sa Su
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30 31
```