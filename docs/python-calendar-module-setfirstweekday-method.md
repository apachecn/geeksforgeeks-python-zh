# Python 日历模块| setfirstweekday()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-setfirst weekday-method/](https://www.geeksforgeeks.org/python-calendar-module-setfirstweekday-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

在 Python 中， **`calendar.setfirstweekday(weekday)`** 是日历模块中为简单文本日历提供的功能。

**`setfirstweekday()`** 方法将工作日(0 为周一，6 为周日)设置为每周开始。为方便起见，提供了值“星期一”、“星期二”、“星期三”、“星期四”、“星期五”、“星期六”和“星期日”。
例如，将第一个工作日设置为周日。

```py
Syntax: setfirstweekday()
Parameter: no parameter
Returns: None
```

**代码#1:**

```py
# Python program to explain working of setfirstweekday() method

# importing calendar module
import calendar

# calling setfirstweekday() function
val = calendar.setfirstweekday(calendar.SUNDAY)

# returns None
print(val)
```

**输出:**

```py
None
```

**代码#2:** 用`prmonth()`方法解释`setfirstweekday()`方法的工作

```py
# Python code to demonstrate the working of 
# setfirstweekday() with prmonth() method

# importing calendar module for calendar operations 
import calendar 

# using prmonth() to print calendar of 1997 
print ("The 4th month of 1997 is : ") 
calendar.prmonth(1997, 4, 2, 1) 

# using setfirstweekday() to set first week day number 
calendar.setfirstweekday(4) 

print ("\r") 

# using firstweekday() to check the changed day 
print ("The new week day number is : ", end ="") 
print (calendar.firstweekday()) 
```

**输出:**

```py
The 4th month of 1997 is : 
     April 1997
Mo Tu We Th Fr Sa Su
    1  2  3  4  5  6
 7  8  9 10 11 12 13
14 15 16 17 18 19 20
21 22 23 24 25 26 27
28 29 30

The new week day number is : 4
```