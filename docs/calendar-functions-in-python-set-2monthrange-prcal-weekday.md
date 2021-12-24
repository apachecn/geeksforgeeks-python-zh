# Python 中的日历函数| Set 2(monthrange()、prcal()、weekday()……)

> 原文:[https://www . geesforgeks . org/calendar-functions-in-python-set-2 month range-prcal-weekday/](https://www.geeksforgeeks.org/calendar-functions-in-python-set-2monthrange-prcal-weekday/)

第 1 集讨论了一些日历功能

**1。monthrange(年、月)** :-该函数返回**两个整数，第一，星期几的起始日(星期一为 0)，第二，月中的天数**。

**2。prcal(year，w，l，c)** :-该功能也**打印特定年份的日历**但不需要“打印”操作来执行。

```py
# Python code to demonstrate the working of
# monthrange() and prcal()

# importing calendar module for calendar operations
import calendar

# using monthrange() to print start week day and 
# number of month
print ("The start week number and no. of days of month : ",end="")
print (calendar.monthrange(2008, 2))

# using prcal() to print calendar of 1997
print ("The calendar of 1997 is : ")
calendar.prcal(1997, 2,1,6)
```

输出:

```py
The start week number and no. of days of month : (4, 29)
The calendar of 1997 is : 
                                  1997

      January                   February                   March
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
       1  2  3  4  5                      1  2                      1  2
 6  7  8  9 10 11 12       3  4  5  6  7  8  9       3  4  5  6  7  8  9
13 14 15 16 17 18 19      10 11 12 13 14 15 16      10 11 12 13 14 15 16
20 21 22 23 24 25 26      17 18 19 20 21 22 23      17 18 19 20 21 22 23
27 28 29 30 31            24 25 26 27 28            24 25 26 27 28 29 30
                                                    31

       April                      May                       June
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
    1  2  3  4  5  6                1  2  3  4                         1
 7  8  9 10 11 12 13       5  6  7  8  9 10 11       2  3  4  5  6  7  8
14 15 16 17 18 19 20      12 13 14 15 16 17 18       9 10 11 12 13 14 15
21 22 23 24 25 26 27      19 20 21 22 23 24 25      16 17 18 19 20 21 22
28 29 30                  26 27 28 29 30 31         23 24 25 26 27 28 29
                                                    30

        July                     August                  September
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
    1  2  3  4  5  6                   1  2  3       1  2  3  4  5  6  7
 7  8  9 10 11 12 13       4  5  6  7  8  9 10       8  9 10 11 12 13 14
14 15 16 17 18 19 20      11 12 13 14 15 16 17      15 16 17 18 19 20 21
21 22 23 24 25 26 27      18 19 20 21 22 23 24      22 23 24 25 26 27 28
28 29 30 31               25 26 27 28 29 30 31      29 30

      October                   November                  December
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
       1  2  3  4  5                      1  2       1  2  3  4  5  6  7
 6  7  8  9 10 11 12       3  4  5  6  7  8  9       8  9 10 11 12 13 14
13 14 15 16 17 18 19      10 11 12 13 14 15 16      15 16 17 18 19 20 21
20 21 22 23 24 25 26      17 18 19 20 21 22 23      22 23 24 25 26 27 28
27 28 29 30 31            24 25 26 27 28 29 30      29 30 31

```

**3。prmonth(年、月、w、l)** :-该功能也**打印特定年份的月份**但不需要“打印”操作来执行。

**4。setfirstweekday(num)** :-该功能设置一周中的**日起始数**。

```py
# Python code to demonstrate the working of
# prmonth() and setfirstweekday()

# importing calendar module for calendar operations
import calendar

# using prmonth() to print calendar of 1997
print ("The 4th month of 1997 is : ")
calendar.prmonth(1997, 4, 2, 1)

# using setfirstweekday() to set first week day number
calendar.setfirstweekday(4)

print ("\r")

# using firstweekday() to check the changed day
print ("The new week day number is : ",end="")
print (calendar.firstweekday())
```

输出:

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

**5。weekday(年、月、日)** :-该函数返回参数中指定日期的**星期几** (0 是星期一)。

```py
# Python code to demonstrate the working of
# weekday()

# importing calendar module for calendar operations
import calendar

# using weekday() to print day number of date
print ("The day number of 25 April 1997 is : ",end="")
print (calendar.weekday(1997,4,25))
```

输出:

```py
The day number of 25 April 1997 is : 4

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。