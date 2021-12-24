# Python 日历模块| firstweekday()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-first weekday-method/](https://www.geeksforgeeks.org/python-calendar-module-firstweekday-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

在 Python 中， **`calendar.firstweekday()`** 是日历模块中为简单文本日历提供的功能**。**

**`firstweekday()`** 方法用于**获取当前设置为每周工作日开始。**

```
Syntax: firstweekday()
Parameter: no parameter
Returns: None
```

**代码#1:**

```
# Python program to explain working of firstweekday() method

# importing calendar module
import calendar

# default firstweekday
print("Default First weekday is - ", calendar.firstweekday())

# setting 2nd day as firstweekday
calendar.setfirstweekday(2)

# print firstweekday
print("First weekday after modification is - ", calendar.firstweekday())
```

**输出:**

```
Default First weekday is -  6
First weekday after modification is -  2
```

**代码#2:** 用 prmonth()方法解释第一个工作日()方法的工作

```
# Python code to demonstrate the working of 
# firstweekday() with help of prmonth() method

# importing calendar module for calendar operations 
import calendar 

# using prmonth() to print calendar of 1997 
print ("The 4th month of 1997 is : ") 
calendar.prmonth(1997, 4, 2, 1) 

# using setfirstweekday() to set first week day number 
calendar.setfirstweekday(4) 

print("First weekday after modification is - ",
                        calendar.firstweekday())
```

**输出:**

```
The 4th month of 1997 is : 
     April 1997
Mo Tu We Th Fr Sa Su
    1  2  3  4  5  6
 7  8  9 10 11 12 13
14 15 16 17 18 19 20
21 22 23 24 25 26 27
28 29 30
 First weekday after modification is -  4

```