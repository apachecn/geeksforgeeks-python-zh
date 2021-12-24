# Python 日历模块:formatmonth()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-format month-method/](https://www.geeksforgeeks.org/python-calendar-module-formatmonth-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

***类* `calendar.TextCalendar(firstweekday=0)`** 可以用来生成纯文本日历。formatmonth()方法是 TextCalendar 实例的方法之一。

**`formatmonth()`**Python 中的方法是用来获取多行字符串中的月历。

> **语法:** formatmonth(年、月、宽=0，行=0)
> 
> **参数:**
> **年份:**日历年
> **月份:**日历月
> **宽度:**【可选】指定日期列的宽度，以
> **行为中心:**【可选】指定每周将使用的行数。
> 
> **返回:**返回一个月的日历。

**代码#1:**

```py
# Python program to demonstrate working of formatmonth() method

# importing calendar module
import calendar

text_cal = calendar.TextCalendar(firstweekday = 0)

year = 2018
month = 9
# default value of width is 0

# printing formatmonth
print(text_cal.formatmonth(year, month))
```

**输出:**

```py
   September 2018
Mo Tu We Th Fr Sa Su
                1  2
 3  4  5  6  7  8  9
10 11 12 13 14 15 16
17 18 19 20 21 22 23
24 25 26 27 28 29 30

```

**代码#2:** 带参数宽度

```py
# Python program to demonstrate working of formatmonth() method

# importing calendar module
import calendar

text_cal = calendar.TextCalendar(firstweekday = 0)

# default value of width is 0

# printing formatmonth
print(text_cal.formatmonth(2018, 9, w = 5))
```

**输出:**

```py
              September 2018
 Mon   Tue   Wed   Thu   Fri   Sat   Sun
                                 1     2
   3     4     5     6     7     8     9
  10    11    12    13    14    15    16
  17    18    19    20    21    22    23
  24    25    26    27    28    29    30
```

**代码#3:**

```py
# Python program to demonstrate working of formatmonth() method

# importing calendar module
import calendar

text_cal = calendar.TextCalendar(firstweekday = 0)

# giving value of width = 6, line = 2

# printing formatmonth
print(text_cal.formatmonth(2018, 10, 6, 2))
```

**输出:**

```py
                  October 2018

 Mon    Tue    Wed    Thu    Fri    Sat    Sun

   1      2      3      4      5      6      7

   8      9     10     11     12     13     14

  15     16     17     18     19     20     21

  22     23     24     25     26     27     28

  29     30     31
```