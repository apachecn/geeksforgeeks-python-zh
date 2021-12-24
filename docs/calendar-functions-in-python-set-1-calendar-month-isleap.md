# Python 中的日历函数|集 1(日历()、月()、is leap()……)

> 原文:[https://www . geesforgeks . org/calendar-functions-in-python-set-1-calendar-month-islap/](https://www.geeksforgeeks.org/calendar-functions-in-python-set-1-calendar-month-isleap/)

Python 定义了一个内置的模块“**日历**，处理与日历相关的操作。
T3 上的操作**日历:**T7**1。日历(年、w、l、c)** :-该功能显示年份、字符宽度、每周行数和分栏数。
**2。firstweekday()** :-该函数返回**第一周的日数**。默认为 0(星期一)。

## 计算机编程语言

```
# Python code to demonstrate the working of
# calendar() and firstweeksday()

# importing calendar module for calendar operations
import calendar

# using calendar to print calendar of year
# prints calendar of 2012
print ("The calendar of year 2012 is : ")
print (calendar.calendar(2012,2,1,6))

#using firstweekday() to print starting day number
print ("The starting day number in calendar is : ",end="")
print (calendar.firstweekday())
```

输出:

```
The calendar of year 2012 is : 
                                  2012

      January                   February                   March
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                   1             1  2  3  4  5                1  2  3  4
 2  3  4  5  6  7  8       6  7  8  9 10 11 12       5  6  7  8  9 10 11
 9 10 11 12 13 14 15      13 14 15 16 17 18 19      12 13 14 15 16 17 18
16 17 18 19 20 21 22      20 21 22 23 24 25 26      19 20 21 22 23 24 25
23 24 25 26 27 28 29      27 28 29                  26 27 28 29 30 31
30 31

       April                      May                       June
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                   1          1  2  3  4  5  6                   1  2  3
 2  3  4  5  6  7  8       7  8  9 10 11 12 13       4  5  6  7  8  9 10
 9 10 11 12 13 14 15      14 15 16 17 18 19 20      11 12 13 14 15 16 17
16 17 18 19 20 21 22      21 22 23 24 25 26 27      18 19 20 21 22 23 24
23 24 25 26 27 28 29      28 29 30 31               25 26 27 28 29 30
30

        July                     August                  September
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
                   1             1  2  3  4  5                      1  2
 2  3  4  5  6  7  8       6  7  8  9 10 11 12       3  4  5  6  7  8  9
 9 10 11 12 13 14 15      13 14 15 16 17 18 19      10 11 12 13 14 15 16
16 17 18 19 20 21 22      20 21 22 23 24 25 26      17 18 19 20 21 22 23
23 24 25 26 27 28 29      27 28 29 30 31            24 25 26 27 28 29 30
30 31

      October                   November                  December
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
 1  2  3  4  5  6  7                1  2  3  4                      1  2
 8  9 10 11 12 13 14       5  6  7  8  9 10 11       3  4  5  6  7  8  9
15 16 17 18 19 20 21      12 13 14 15 16 17 18      10 11 12 13 14 15 16
22 23 24 25 26 27 28      19 20 21 22 23 24 25      17 18 19 20 21 22 23
29 30 31                  26 27 28 29 30            24 25 26 27 28 29 30
                                                    31

The starting day number in calendar is : 0
```

**3。isleap(年份)** :-该函数检查参数中提到的年份是否为a **闰年**。
**4。leapdays (year1，year2)** :-该函数在参数中返回指定年份之间的**闰日数。** 

## 计算机编程语言

```
# Python code to demonstrate the working of
# isleap() and leapdays()

# importing calendar module for calendar operations
import calendar

# using isleap() to check if year is leap or not
if (calendar.isleap(2008)):
       print ("The year is leap")
else : print ("The year is not leap")

#using leapdays() to print leap days between years
print ("The leap days between 1950 and 2000 are : ",end="")
print (calendar.leapdays(1950, 2000))
```

输出:

```
The year is leap
The leap days between 1950 and 2000 are : 12
```

**5。月(年、月、w、l)** :-该函数打印参数中提到的特定年份的**月。**一周取 4 个参数，年、月、字宽、行数**。** 

## 计算机编程语言

```
# Python code to demonstrate the working of
# month()

# importing calendar module for calendar operations
import calendar

# using month() to display month of specific year
print ("The month 5th of 2016 is :")
print (calendar.month(2016,5,2,1))
```

输出:

```
The month 5th of 2016 is :
      May 2016
Mo Tu We Th Fr Sa Su
                   1
 2  3  4  5  6  7  8
 9 10 11 12 13 14 15
16 17 18 19 20 21 22
23 24 25 26 27 28 29
30 31
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。