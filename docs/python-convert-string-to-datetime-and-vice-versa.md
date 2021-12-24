# Python |将字符串转换为日期时间，反之亦然

> 原文:[https://www . geesforgeks . org/python-convert-string-to-datetime-反之亦然/](https://www.geeksforgeeks.org/python-convert-string-to-datetime-and-vice-versa/)

编写一个 Python 程序，将给定的字符串转换为日期时间，反之亦然。

**使用`strptime()`函数将字符串转换为日期时间的程序。**

**示例:**

```
Input : Dec 4 2018 10:07AM 
Output : 2018-12-04 10:07:00

Input : Jun 12 2013 5:30PM 
Output : 2013-06-12 17:30:00

```

`strptime()`在日期时间和时间模块中可用，用于日期时间转换。该函数将日期时间的给定字符串更改为所需的格式。

**语法:**

```
datetime.strptime(date_string, format)
```

参数`date_string` 和*格式*应该是字符串类型。

```
import datetime

# Function to convert string to datetime
def convert(date_time):
    format = '%b %d %Y %I:%M%p' # The format
    datetime_str = datetime.datetime.strptime(date_time, format)

    return datetime_str

# Driver code
date_time = 'Dec 4 2018 10:07AM'
print(convert(date_time))
```

**输出:**

```
2018-12-04 10:07:00
```

**将日期时间转换为字符串的程序**
**示例:**

```
Input : 2018-12-04 10:07:00  
Output : Dec 4 2018 10:07:00AM 

Input : 2013-06-12 17:30:00Jun 12 2013 5:30PM 
Output : Jun 12 2013 5:30:00PM 

```

Python `strftime()`函数存在于日期时间和时间模块中，用于基于指定的格式字符串创建字符串表示。

**语法:**

```
datetime_object.strftime(format_str)
```

另一个类似的功能在时间模块中可用，它将元组或`struct_time` 对象转换为由格式参数指定的字符串。

```
import time

# Function to convert string to datetime
def convert(datetime_str):
    datetime_str = time.mktime(datetime_str)

    format = "%b %d %Y %r" # The format
    dateTime = time.strftime(format, time.gmtime(datetime_str))
    return dateTime

# Driver code
date_time = (2018, 12, 4, 10, 7, 00, 1, 48, 0)
print(convert(date_time))
```

**输出:**

```
Dec 04 2018 10:07:00 AM
```