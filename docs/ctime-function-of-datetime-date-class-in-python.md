# Python 中 Datetime.date 类的 ctime()函数

> 原文:[https://www . geeksforgeeks . org/ctime-datetime-date-class-in-python/](https://www.geeksforgeeks.org/ctime-function-of-datetime-date-class-in-python/)

**ctime()** 函数用于返回包含日期和时间的字符串。

> 语法:受害者()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回包含日期和时间的字符串。

**字符串表示的格式:**

*   字符串长度为 24 个字符。
*   周被打印为三个字母的单词。

```
Sun, Mo, Tue, Wed, Thu, Fri, Sat
```

*   月份用三位数的字母表示

```
Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec
```

*   一个月中的某一天用两位数表示
*   时间以 HH:MM:SS 格式表示
*   年份是一个 4 位数

**示例 1:** 获取包含日期和时间的字符串

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting a string containing
# the date and time

# Importing datetime and time module 
import datetime
import time

# Calling the time() function
# to return current time
Todays_time = time.time()

# Printing today's time
print(Todays_time)

# Calling the fromtimestamp() function
# to get date from the current time
date_From_CurrentTime = datetime.date.fromtimestamp(Todays_time);

# Printing the current date
print("Date for Timestamp used is: %s"%date_From_CurrentTime);

# Calling the ctime() function over the above date
print("Today's date: %s"%date_From_CurrentTime.ctime());
```

**输出:**

```
1627282355.0111642
Date for Timestamp used is: 2021-07-26
Today's date: Mon Jul 26 00:00:00 2021
```

**示例 2:** 获取包含日期和时间的字符串

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting a string containing
# the date and time

# Importing datetime module 
import datetime

# Initializing a date object for a 
# different date
Date = datetime.date(2013, 2, 10);

# Calling the ctime() function 
# over the above date
print("The date: %s"%Date.ctime());
```

**输出:**

```
The date: Sun Feb 10 00:00:00 2013
```