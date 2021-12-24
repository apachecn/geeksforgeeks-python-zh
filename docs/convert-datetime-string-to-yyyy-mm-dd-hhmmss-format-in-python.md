# 将日期时间字符串转换为 Python 中的 YYYY-MM-DD-HH:MM:SS 格式

> 原文:[https://www . geesforgeks . org/convert-datetime-string-to-yyyy-mm-DD-hhmmss-format-in-python/](https://www.geeksforgeeks.org/convert-datetime-string-to-yyyy-mm-dd-hhmmss-format-in-python/)

在本文中，我们将把日期时间字符串转换成%Y-%m-%d-%H:%M:%S 格式。对于此任务，使用 str time()和 str time()函数。

**strptime()** 用于将日期时间字符串转换为年-月-日小时分钟和秒钟格式的日期时间

**语法:**

> datetime.strptime（my_date， "%d-%b-%Y-%H：%M：%S"）

**str time()**用于将 DateTime 转换为所需的时间戳格式

**语法**:

> datetime.strftime（"%Y-%m-%d-%H：%M：%S"）

在这里，

*   &Y 表示年份
*   %m 表示月份
*   %d 表示日
*   %H 表示小时
*   %M 表示分钟
*   %S 表示秒。

首先，将日期时间时间戳作为字符串。然后，使用 strptime()将其转换为 DateTime。现在，使用 strftime 转换为所需的日期时间格式

**示例 1:** 将 DateTime 字符串转换为%Y-%m-%d-%H:%M:%S 格式的 Python 程序

## 蟒蛇 3

```py
# import datetime module
from datetime import datetime

# consider date in string format
my_date = "30-May-2020-15:59:02"

# convert datetime string into date,month,day and
# hours:minutes:and seconds format using strptime
d = datetime.strptime(my_date, "%d-%b-%Y-%H:%M:%S")

# convert datetime format into %Y-%m-%d-%H:%M:%S
# format using strftime
print(d.strftime("%Y-%m-%d-%H:%M:%S"))
```

**输出**

```py
'2020-05-30-15:59:02'
```

**示例 2:** 将 DateTime 字符串转换为%Y-%m-%d-%H:%M:%S 格式的 Python 程序

## 蟒蛇 3

```py
# import datetime module
from datetime import datetime

# consider date in string format
my_date = "30-May-2020-15:59:02"

# convert datetime string into date,month,day 
# and hours:minutes:and seconds format using
# strptime
d = datetime.strptime(my_date, "%d-%b-%Y-%H:%M:%S")

# convert datetime format into %Y-%m-%d-%H:%M:%S
# format using strftime
print(d.strftime("%Y-%m-%d-%H:%M:%S"))

# consider date in string format
my_date = "04-Jan-2021-02:45:12"

# convert datetime string into date,month,day 
# and hours:minutes:and seconds format using 
# strptime
d = datetime.strptime(my_date, "%d-%b-%Y-%H:%M:%S")

# convert datetime format into %Y-%m-%d-%H:%M:%S 
# format using strftime
print(d.strftime("%Y-%m-%d-%H:%M:%S"))

# consider date in string format
my_date = "23-May-2020-15:59:02"

# convert datetime string into date,month,day and 
# hours:minutes:and seconds format using strptime
d = datetime.strptime(my_date, "%d-%b-%Y-%H:%M:%S")

# convert datetime format into %Y-%m-%d-%H:%M:%S 
# format using strftime
print(d.strftime("%Y-%m-%d-%H:%M:%S"))
```

**Output**

```py
2020-05-30-15:59:02
2021-01-04-02:45:12
2020-05-23-15:59:02

```