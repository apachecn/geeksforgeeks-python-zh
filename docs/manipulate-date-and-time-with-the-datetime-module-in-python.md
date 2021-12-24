# 使用 Python 中的日期时间模块操纵日期和时间

> 原文:[https://www . geeksforgeeks . org/operate-date-time-with-datetime-in-python 模块/](https://www.geeksforgeeks.org/manipulate-date-and-time-with-the-datetime-module-in-python/)

你有没有想过用 Python 处理日期和时间？如果您已经这样做了，那么您一定注意到 Python 没有提供任何内置的方法来处理日期或时间。但是由于预装了 Python 标准实用程序模块的 **DateTime** 模块，我们可以根据自己的需要轻松操作日期和时间。我们甚至可以执行诸如获取当前日期、添加或减去日期和时间等操作。

在本文中，我们将学习使用 Python 中的[**【DateTime】**](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)模块可以在日期和时间上执行的所有操作。因此，在开始之前，让我们看看 DateTime 模块及其包含的类的基础知识。

日期时间类别分为 6 个主要类别–

*   **日期–**一个理想化的天真日期，假设当前公历一直有效，并且将一直有效。它的属性是年、月、日。
*   **时间–**一个理想化的时间，独立于任何特定的一天，假设每天正好有 24*60*60 秒。它的属性是小时、分钟、秒、微秒和 tzinfo。
*   **datetime–**它是日期和时间以及年、月、日、小时、分钟、秒、微秒和 tzinfo 属性的组合。
*   **时间增量–**一个持续时间，表示两个日期、时间或日期时间实例之间的差异，分辨率为微秒。
*   **tzinfo–**提供时区信息对象。
*   **时区–**一个实现 tzinfo 抽象基类的类，作为与世界协调时的固定偏移量(3.2 版本中新增)。

## 获取当前日期和时间

为了获得当前日期和时间**日期时间，使用了 now()** 方法。它返回本地当前日期和时间。

**语法:**

> date . now(tz)

**示例:**

## 蟒蛇 3

```
# Python3 code to demonstrate 
# Getting current date and time using 
# now(). 

# importing datetime module for now() 
import datetime 

# using now() to get current time 
current_time = datetime.datetime.now() 

# Printing value of now. 
print ("Time now at greenwich meridian is : ", end = "") 
print (current_time) 
```

**输出:**

```
Time now at greenwich meridian is : 2021-03-16 17:59:03.837572
```

now()函数有各种属性，可以从上面的输出中给出所需的细节。一些属性是年、月、日、时、分、秒。为了更好的理解，请看下面的例子。

**示例:**

## 蟒蛇 3

```
# Python3 code to demonstrate 
# attributes of now() 

# importing datetime module for now() 
import datetime 

# using now() to get current time 
current_time = datetime.datetime.now() 

# Printing attributes of now(). 
print ("The attributes of now() are : ") 

print ("Year : ", end = "") 
print (current_time.year) 

print ("Month : ", end = "") 
print (current_time.month) 

print ("Day : ", end = "") 
print (current_time.day) 

print ("Hour : ", end = "") 
print (current_time.hour) 

print ("Minute : ", end = "") 
print (current_time.minute) 

print ("Second : ", end = "") 
print (current_time.second) 

print ("Microsecond : ", end = "") 
print (current_time.microsecond)
```

**输出:**

```
The attributes of now() are : 
Year : 2021
Month : 3
Day : 16
Hour : 18
Minute : 1
Second : 59
Microsecond : 490402
```

### 仅获取当前日期

DateTime 模块还提供了另一个名为 **today()** 的方法，只打印今天日期的值。

**示例:**

## 蟒蛇 3

```
# Python program to get 
# current date 

# Import date class from datetime module 
from datetime import date 

# Returns the current local date 
today = date.today() 
print("Today date is: ", today)
```

**输出:**

```
Today date is:  2021-03-16
```

### 仅获取当前时间

我们可以使用 **time()** 函数创建一个时间对象。考虑下面的例子。

**示例:**

## 蟒蛇 3

```
from datetime import datetime 

# Time object containing 
# the current time. 
time = datetime.now().time() 

print("Current Time =", time)
```

**输出:**

```
Current Time = 18:13:35.003918
```

请参考下面的文章，获取有关获取当前日期和时间的详细信息。

*   [使用 Python 获取当前日期和时间](https://www.geeksforgeeks.org/get-current-date-and-time-using-python/)
*   [使用 Python 获取当前日期](https://www.geeksforgeeks.org/get-current-date-using-python/)
*   [Python 程序获取当前时间](https://www.geeksforgeeks.org/python-program-to-get-current-time/)
*   [使用 Python 获取当前时间(单位为毫秒)](https://www.geeksforgeeks.org/get-current-time-in-milliseconds-using-python/)
*   [使用 Python 获取不同时区的当前时间](https://www.geeksforgeeks.org/get-current-time-in-different-timezone-using-python/)

## 格式化日期和时间

在世界各个地区，使用不同类型的日期格式。DateTime 提供了[**【str time()】**](https://www.geeksforgeeks.org/python-strftime-function/)**的方法来处理这样的格式化。此函数用于将日期和时间对象转换为其字符串表示形式。它接受一个或多个格式化代码输入，并返回字符串表示形式。**

****语法:****

> **strftime（format）**

****示例:****

## **蟒蛇 3**

```
# Python program to demonstrate 
# strftime() function 

from datetime import datetime

# Getting current date and time 
now = datetime.now() 
print("Without formatting", now) 

# Example 1 
s = now.strftime("%a %m %y") 
print('\nExample 1:', s) 

# Example 2 
s = now.strftime("%A %-m %Y") 
print('\nExample 2:', s) 

# Example 3 
s = now.strftime("%-I %p %S") 
print('\nExample 3:', s) 

# Example 4 
s = now.strftime("%-j") 
print('\nExample 4:', s)
```

****输出:****

```
Without formatting 2021-03-16 18:28:59.055609

Example 1: Tue 03 21

Example 2: Tuesday 3 2021

Example 3: 6 PM 59

Example 4: 75
```

**请参考下面的文章，以获得关于在 Python 中格式化日期和时间的详细信息。**

*   **[在 Python 中格式化日期](https://www.geeksforgeeks.org/formatting-dates-in-python/)**

## **处理时间增量对象**

**Python **timedelta()** 函数存在于 datetime 库下，通常用于计算日期的差异，也可以用于 Python 中的日期操作。**

****语法:****

> **时间增量(天=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)**

****示例:****

## **蟒蛇 3**

```
# import datetime
from datetime import timedelta

# create timedelta object with difference 
# of 1 weeks
d1 = timedelta(weeks=1)

# create timedelta object with difference 
# of 1 weeks
d2 = timedelta(days=30)

print(d1)
print(d2)
```

****输出:****

```
7 days, 0:00:00
30 days, 0:00:00
```

**我们还可以使用 **+** 和**–**运算符从日期时间对象中添加或减去时间增量对象。**

****示例:****

## **蟒蛇 3**

```
# Timedelta function demonstration 

from datetime import datetime, timedelta 

# Using current time 
ini_time_for_now = datetime.now() 

# printing initial_date 
print ("initial_date", str(ini_time_for_now)) 

# Calculating future dates 
# for two years 
future_date_after_2yrs = ini_time_for_now + timedelta(days = 730) 

future_date_after_2days = ini_time_for_now + timedelta(days = 2) 

# printing calculated future_dates 
print('future_date_after_2yrs:', str(future_date_after_2yrs)) 
print('future_date_after_2days:', str(future_date_after_2days)) 
```

****输出:****

```
initial_date 2021-03-16 18:47:53.103230
future_date_after_2yrs: 2023-03-16 18:47:53.103230
future_date_after_2days: 2021-03-18 18:47:53.103230
```

****注意:**输出将是一个 DateTime 对象。**

### **两个日期之间的差异**

**如上所述，timedelta 对象表示两个日期之间的差异。我们可以从一个日期减去另一个日期，结果将是一个时间增量对象。**

****例 1:****

## **蟒蛇 3**

```
# import datetime
from datetime import date

# Create two dates with year, month, 
# date
d1 = date(2021, 3, 16)
d2 = date(2021, 3, 31)

# Difference between two dates
diff = d2 - d1

print("Difference: ", diff.days)
```

****输出:****

```
Difference:  15
```

****例 2:****

## **蟒蛇 3**

```
# import datetime
from datetime import datetime

# Create two dates with year, month, 
# date, hour, minute, seconds
d1 = datetime(2021, 3, 16, 19, 6, 6)
d2 = datetime(2021, 3, 31, 12, 2, 2)

# Difference between two dates
diff = d2 - d1

print("Difference: ", diff)
```

****输出:****

```
Difference:  14 days, 16:55:56
```

**请参考下面的文章，获取有关查找日期差异的详细信息。**

*   **[使用 datetime.timedelta()方法的两个日期之间的差异(以分钟为单位)](https://www.geeksforgeeks.org/python-difference-between-two-dates-in-minutes-using-datetime-timedelta-method/)**
*   **[Python 程序查找两个给定日期之间的天数](https://www.geeksforgeeks.org/python-program-to-find-number-of-days-between-two-given-dates/)**

## **比较日期**

**日期也可以使用比较运算符进行比较(如，<=, > =，！=等等。)**

****示例 1:** 使用比较运算符**

## **蟒蛇 3**

```
# Simple Python program to compare dates 

# importing datetime module 
import datetime 

# date in yyyy/mm/dd format 
d1 = datetime.datetime(2018, 5, 3) 
d2 = datetime.datetime(2018, 6, 1) 

# Comparing the dates will return 
# either True or False 
print("d1 is greater than d2 : ", d1 > d2) 
print("d1 is less than d2 : ", d1 < d2) 
print("d1 is not equal to d2 : ", d1 != d2)
```

****输出:****

```
d1 is greater than d2 :  False
d1 is less than d2 :  True
d1 is not equal to d2 :  True
```

**参考下面的文章来获得关于比较日期的详细信息。**

*   **[在 Python 中比较日期](https://www.geeksforgeeks.org/comparing-dates-python/)**

## **使用不同的时区**

**datetime.now()没有任何关于时区的信息。它只是使用当前的系统时间。在某些情况下，可能需要时区详细信息。在这种情况下，使用 tzinfo 抽象类。tzinfo 是一个抽象基类。它不能直接实例化。一个具体的子类必须派生它并实现这个抽象类提供的方法。**

### **天真和感知日期时间对象**

**不包含任何时区信息的日期时间对象被称为幼稚日期时间对象。对于初始日期时间对象，日期时间对象. tzinfo 将为无。感知日期时间对象包含嵌入其中的时区信息。**

**tzinfo 基类中可实现的方法有:**

*   ****utcoffset():** 它返回作为参数传递的 datetime 实例的偏移量。它是指时区偏移，表示时区比协调世界时或世界时坐标(UTC)提前多少小时。偏移量写成+00:00。例如:对于亚洲/台北，写成 UTC +08:00。**
*   ****dst():** 简写为日光节约时间。它表示在夏季将时钟提前 1 小时，这样黑暗会根据时钟晚些时候降临。它被设置为开或关。它基于包含 9 个元素的元组进行检查，如下所示:**

> **(dt.year，dt.month，dt.day，dt.hour，dt.minute，dt.second，dt.weekday()，0，0)**

*   ****tzname():** 用于查找传递的 datetime 对象的时区名称。它返回一个 Python 字符串对象。**
*   ****fromutc():** 此函数采用 utc 中对象的日期和时间，并返回等效的本地时间。它主要用于调整日期和时间。它是从默认的 datetime.astimezone()实现中调用的。dt.tzinfo 将作为自身传递，dt 的日期和时间数据将作为等效的当地时间返回。**

****示例:****

## **蟒蛇 3**

```
import datetime as dt 
from dateutil import tz 

tz_string = dt.datetime.now(dt.timezone.utc).astimezone().tzname() 

print("datetime.now() :", tz_string) 

NYC = tz.gettz('Europe / Berlin') 
dt1 = dt.datetime(2015, 5, 21, 12, 0) 
dt2 = dt.datetime(2015, 12, 21, 12, 0, tzinfo = NYC) 

print("Naive Object :", dt1.tzname()) 
print("Aware Object :", dt2.tzname())
```

****输出:****

```
datetime.now() : UTC
Naive Object : None
Aware Object : CET
```

**我们也可以使用 **pytz** 模块来处理跨时区转换。让我们看看它是如何工作的。**

### **使用 Pytz**

**[**Pytz**](https://www.geeksforgeeks.org/python-pytz/) 将 Olson tz 数据库引入 Python，因此支持几乎所有时区。该模块提供日期时间转换功能，并帮助用户服务于国际客户群。**

**通过使用 **astimezone()** 函数，我们可以将时间转换为不同的时区。**

****语法:****

> **astimezone（t）**

****示例:****

## **蟒蛇 3**

```
from datetime import datetime 
from pytz import timezone 

format = "%Y-%m-%d %H:%M:%S %Z%z"

# Current time in UTC 
now_utc = datetime.now(timezone('UTC')) 
print(now_utc.strftime(format)) 

# Convert to Asia/Kolkata time zone 
now_asia = now_utc.astimezone(timezone('Asia/Kolkata')) 
print(now_asia.strftime(format))
```

****输出:****

```
2021-03-17 07:41:19 UTC+0000
2021-03-17 13:11:19 IST+0530
```

**请参考下面的文章，获取有关使用时区的详细信息。**

*   **[python–datetime . tzinfo()](https://www.geeksforgeeks.org/python-datetime-tzinfo/)**
*   **[Python |时区转换](https://www.geeksforgeeks.org/python-timezone-conversion/)**
*   **[Python pytz](https://www.geeksforgeeks.org/python-pytz/)**