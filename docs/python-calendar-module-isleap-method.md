# Python 日历模块| isleap()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-islap-method/](https://www.geeksforgeeks.org/python-calendar-module-isleap-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

在 Python 中， **`calendar.isleap()`** 是日历模块中为简单文本日历提供的功能。

**`isleap()`** 法是用来取值 True 的**如果年份是闰年，否则给出 False。**

```
Syntax: isleap()
Parameter: 
year: Year to be tested leap or not.

Returns: Returns True if the year is a leap year, otherwise False.
```

**代码#1:**

```
# Python program to explain working of isleap() method

# importing calendar module
import calendar

# checking whether given year is leap or not
print(calendar.isleap(2016))
print(calendar.isleap(2001))
```

**输出:**

```
True
False
```

**代码#2:** 解释`isleap()`方法的工作。

下面的代码打印第 4 个月的日历，如果给定的年份是年，否则通知年份不是闰年。

```
# Python code to demonstrate the working of isleap() 

# importing calendar module for calendar operations 
import calendar 

year = 2017

# calling isleap() method to verify
val = calendar.isleap(year)

# checking the condition is True or not
if val == True:

    # print 4th month of given leap year 
    calendar.prmonth(year, 4, 2, 1) 

# Returned False, year is not a leap
else:
    print("% s is not a leap year" % year)
```

**输出:**

```
2017 is not a leap year
```