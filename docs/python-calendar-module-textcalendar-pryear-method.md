# Python 日历模块:TextCalendar pryear()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-text calendar-pr year-method/](https://www.geeksforgeeks.org/python-calendar-module-textcalendar-pryear-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

***类* `calendar.TextCalendar(firstweekday=0)`** 可以用来生成纯文本日历。 **pryear()** 方法是 TextCalendar 实例的方法之一。

Python 中的 **`pryear()`** 方法用于打印`formatmonth()`返回的全年日历。

> **语法:** pryear(年，宽=2，行=1，c=6，m=3)
> 
> **参数:**
> **年份:**日历年
> **宽度:**【可选】指定日期栏
> **行的宽度:**【可选】指定每周将使用的行数。
> **c:** 【可选】月列间空格数
> **m:** 【可选】连续月数
> 
> **返回:**返回一整年的 m 列日历。

**代码#1:**

```py
# Python program to demonstrate working of pryear() method

# importing calendar module 
import calendar 

text_cal = calendar.TextCalendar(firstweekday = 0) 

year = 2018
width = 4

# printing pryear
print(text_cal.pryear(year, width)) 
```

**输出:**

```py
                                                       2018

             January                                 February                                 March
Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun
  1    2    3    4    5    6    7                        1    2    3    4                        1    2    3    4
  8    9   10   11   12   13   14         5    6    7    8    9   10   11         5    6    7    8    9   10   11
 15   16   17   18   19   20   21        12   13   14   15   16   17   18        12   13   14   15   16   17   18
 22   23   24   25   26   27   28        19   20   21   22   23   24   25        19   20   21   22   23   24   25
 29   30   31                            26   27   28                            26   27   28   29   30   31

              April                                    May                                     June
Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun
                                1              1    2    3    4    5    6                             1    2    3
  2    3    4    5    6    7    8         7    8    9   10   11   12   13         4    5    6    7    8    9   10
  9   10   11   12   13   14   15        14   15   16   17   18   19   20        11   12   13   14   15   16   17
 16   17   18   19   20   21   22        21   22   23   24   25   26   27        18   19   20   21   22   23   24
 23   24   25   26   27   28   29        28   29   30   31                       25   26   27   28   29   30
 30

               July                                   August                                September
Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun
                                1                   1    2    3    4    5                                  1    2
  2    3    4    5    6    7    8         6    7    8    9   10   11   12         3    4    5    6    7    8    9
  9   10   11   12   13   14   15        13   14   15   16   17   18   19        10   11   12   13   14   15   16
 16   17   18   19   20   21   22        20   21   22   23   24   25   26        17   18   19   20   21   22   23
 23   24   25   26   27   28   29        27   28   29   30   31                  24   25   26   27   28   29   30
 30   31

             October                                 November                                December
Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun       Mon  Tue  Wed  Thu  Fri  Sat  Sun
  1    2    3    4    5    6    7                        1    2    3    4                                  1    2
  8    9   10   11   12   13   14         5    6    7    8    9   10   11         3    4    5    6    7    8    9
 15   16   17   18   19   20   21        12   13   14   15   16   17   18        10   11   12   13   14   15   16
 22   23   24   25   26   27   28        19   20   21   22   23   24   25        17   18   19   20   21   22   23
 29   30   31                            26   27   28   29   30                  24   25   26   27   28   29   30
                                                                                 31

```

请注意，可以生成日历的最早年份取决于平台。

**代码#2:** 由于 m=2，所以一行显示的月数为 2。

```py
# Python program to demonstrate working of pryear() method 

# importing calendar module 
import calendar 

text_cal = calendar.TextCalendar(firstweekday = 0) 

# default value of width is 0 

# printing pryear
print(text_cal.pryear(2018, 5, c = 3, m = 2)) 
```

**输出:**

```py
                                         2018

                 January                                     February
 Mon   Tue   Wed   Thu   Fri   Sat   Sun     Mon   Tue   Wed   Thu   Fri   Sat   Sun
   1     2     3     4     5     6     7                         1     2     3     4
   8     9    10    11    12    13    14       5     6     7     8     9    10    11
  15    16    17    18    19    20    21      12    13    14    15    16    17    18
  22    23    24    25    26    27    28      19    20    21    22    23    24    25
  29    30    31                              26    27    28

                  March                                       April
 Mon   Tue   Wed   Thu   Fri   Sat   Sun     Mon   Tue   Wed   Thu   Fri   Sat   Sun
                     1     2     3     4                                           1
   5     6     7     8     9    10    11       2     3     4     5     6     7     8
  12    13    14    15    16    17    18       9    10    11    12    13    14    15
  19    20    21    22    23    24    25      16    17    18    19    20    21    22
  26    27    28    29    30    31            23    24    25    26    27    28    29
                                              30

                   May                                         June
 Mon   Tue   Wed   Thu   Fri   Sat   Sun     Mon   Tue   Wed   Thu   Fri   Sat   Sun
         1     2     3     4     5     6                               1     2     3
   7     8     9    10    11    12    13       4     5     6     7     8     9    10
  14    15    16    17    18    19    20      11    12    13    14    15    16    17
  21    22    23    24    25    26    27      18    19    20    21    22    23    24
  28    29    30    31                        25    26    27    28    29    30

                   July                                       August
 Mon   Tue   Wed   Thu   Fri   Sat   Sun     Mon   Tue   Wed   Thu   Fri   Sat   Sun
                                       1                   1     2     3     4     5
   2     3     4     5     6     7     8       6     7     8     9    10    11    12
   9    10    11    12    13    14    15      13    14    15    16    17    18    19
  16    17    18    19    20    21    22      20    21    22    23    24    25    26
  23    24    25    26    27    28    29      27    28    29    30    31
  30    31

                September                                    October
 Mon   Tue   Wed   Thu   Fri   Sat   Sun     Mon   Tue   Wed   Thu   Fri   Sat   Sun
                                 1     2       1     2     3     4     5     6     7
   3     4     5     6     7     8     9       8     9    10    11    12    13    14
  10    11    12    13    14    15    16      15    16    17    18    19    20    21
  17    18    19    20    21    22    23      22    23    24    25    26    27    28
  24    25    26    27    28    29    30      29    30    31

                 November                                    December
 Mon   Tue   Wed   Thu   Fri   Sat   Sun     Mon   Tue   Wed   Thu   Fri   Sat   Sun
                     1     2     3     4                                     1     2
   5     6     7     8     9    10    11       3     4     5     6     7     8     9
  12    13    14    15    16    17    18      10    11    12    13    14    15    16
  19    20    21    22    23    24    25      17    18    19    20    21    22    23
  26    27    28    29    30                  24    25    26    27    28    29    30
                                              31

None
```