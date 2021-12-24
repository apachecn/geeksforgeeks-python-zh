# Python 中 Datetime.date 类的 fromtimestamp()函数

> 原文:[https://www . geesforgeks . org/frontimestamp-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/fromtimestamp-function-of-datetime-date-class-in-python/)

**frontimestamp()**函数用于返回指定时间戳对应的日期。

**注意:**这里的时间戳是从 1970 年到 2038 年，如果时间戳中有闰秒，这个函数不考虑。这个函数是一个类方法。

> **语法:** @classmethod fromtimestamp(时间戳)
> 
> **参数:**该函数接受如下所示的参数:
> 
> *   **时间戳:**这是要返回日期的指定时间戳。
> 
> **返回值:**该函数返回指定时间戳对应的日期。

**示例 1:** 获取对应于某个纪元的日期& Unix 时间戳。**T3】**

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting a date corresponding
# to a specified timestamp

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
print("Date for the Timestamp is: %s"%date_From_CurrentTime);
```

**输出:**

```
1627279008.95
Date for the Timestamp is: 2021-07-26
```

**示例 2:** 获取指定时间戳对应的日期。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Getting a date corresponding
# to a specified timestamp

# Importing datetime and time module 
import datetime
import time

# Initializing a timestamp value
Timestamp = 1323456464;

# Calling the fromtimestamp() function
# over the above specified Timestamp
date_From_Timestamp = datetime.date.fromtimestamp(Timestamp);

# Printing the date
print("Date for the Timestamp is: %s"%date_From_Timestamp);
```

**输出:**

```
Date for the Timestamp is: 2011-12-09
```