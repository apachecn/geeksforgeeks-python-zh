# Python DateTime – strptime（） 函数

> [https://www.geeksforgeeks.org/python-datetime-strptime-function/](https://www.geeksforgeeks.org/python-datetime-strptime-function/)

**strptime()** 是 DateTime 中另一种可用的方法，用于将字符串格式的时间戳格式化为日期时间对象。

> **语法**:datetime . strptime(time _ data，format_data)
> 
> **参数:**
> 
> *   timedate 是以字符串格式显示的时间
> *   format_data 是以 datetime 格式呈现的数据，它是使用此函数从 time_data 转换而来的。

## **str time()是如何工作的？**

这个函数有两个参数，一个是给定时间的字符串，另一个是格式代码，要将这个字符串转换成，这个字符串会按照下面给出的代码列表转换成日期时间对象。

**格式代码**

<figure class="table">

| **格式代码** | **意为** | **例** |
| --- | --- | --- |
| %a | 缩写的工作日名称 | 珊，我的天 |
| %A | 完整的工作日名称 | 星期天，星期一 |
| %w | 以十进制数表示的工作日 | 0…6 |
| %d | 以零填充十进制表示的一个月中的某一天 | 01, 02 |
| %-d | 以十进制数表示的一个月中的某一天 | 1, 2 .. |
| %b | 缩写的月份名称 | 一月，二月 |
| %m | 月是零填充的十进制数 | 01, 02 |
| %-m | 以十进制数表示的月份 | 1, 2 |
| %B | 完整月份名称 | 一月，二月 |
| %y | 没有世纪的年份作为零填充的十进制数 | 99, 00  |
| %-y | 没有世纪作为十进制数的年份 | 0, 99 |
| %Y | 以世纪为十进制数的年份 | 2000, 1999 |
| %H | 小时(24 小时制)作为零填充十进制数 | 01, 23 |
| %-H | 小时(24 小时制)作为十进制数 | 1, 23 |
| %I | 小时(12 小时制)作为零填充十进制数 | 01, 12 |
| %-我 | 十进制数形式的小时(12 小时制) | 1, 12 |
| %p | 区域设置的上午或下午 | 上午，下午 |
| %M | 分钟作为零填充的十进制数 | 01, 59 |
| %-M | 分钟作为十进制数 | 1, 59 |
| %S | 第二个是零填充的十进制数 | 01, 59 |
| %-S | 第二个十进制数 | 1, 59 |
| %f | 微秒为十进制数，左边填充零 | 000000, 999999 |
| %z | 世界协调时偏移量，格式为+HHMM 或-HHMM |   |
| %Z | 时区名称 |   |
| %j | 以零填充的十进制数表示的一年中的某一天 | 001, 365 |
| %-j | 以十进制数表示的一年中的某一天 | 1, 365 |
| %U | 一年中的第几周(星期日是第一周) | 0, 6 |
| %W | 一年中的周数 | 00, 53 |
| %c | 区域设置的适当日期和时间表示 | 我的九月三十日 07:06:05 2013 |
| %x | 区域设置的适当日期表示 | 11/30/98 |
| %X | 区域的适当时间表示 | 10:03:43 |
| %% | 文字“%”字符 | % |

</figure>

**示例 1:** Python 程序读取 datetime 并使用 strptime 获取所有时间数据。这里，我们将采用字符串格式的时间数据，并提取小时、分钟、秒和毫秒

## 蟒蛇 3

```
# import datetime module from datetime
from datetime import datetime

# consider the time stamp in string format
# DD/MM/YY H:M:S.micros
time_data = "25/05/99 02:35:5.523"

# format the string in the given format :
# day/month/year hours/minutes/seconds-micro
# seconds
format_data = "%d/%m/%y %H:%M:%S.%f"

# Using strptime with datetime we will format
# string into datetime
date = datetime.strptime(time_data, format_data)

# display milli second
print(date.microsecond)

# display hour
print(date.hour)

# display minute
print(date.minute)

# display second
print(date.second)

# display date
print(date)
```

**输出:**

> Five hundred and twenty-three thousand
> 
> Two
> 
> Thirty-five
> 
> five
> 
> 1999-05-25 02:35:05.523000

**示例 2:** 使用 strptime 的 Python 代码。在这里，我们将以字符串格式获取时间数据，并以“%d/%m/%y %H:%M:%S.%f”格式提取时间戳。

## 蟒蛇 3

```
# import datetime module from datetime
from datetime import datetime

# consider the time stamps from a list  in string
# format DD/MM/YY H:M:S.micros
time_data = ["25/05/99 02:35:8.023", "26/05/99 12:45:0.003",
             "27/05/99 07:35:5.523", "28/05/99 05:15:55.523"]

# format the string in the given format : day/month/year 
# hours/minutes/seconds-micro seconds
format_data = "%d/%m/%y %H:%M:%S.%f"

# Using strptime with datetime we will format string
# into datetime
for i in time_data:
    print(datetime.strptime(i, format_data))
```

**输出:**

> 1999-05-25 02:35:08.023000
> 
> 1999-05-26 12:45:00.003000
> 
> 1999-05-27 07:35:05.523000
> 
> 1999-05-28 05:15:55.523000

我们可以通过使用 strptime()本身来获得一个包含所有日期的结构之后的时间。

**语法**:

> time.strptime(时间戳，' %d/%m/%y %H:%M:%S ')

其中时间戳包括时间和日期

**示例**:结构中获取时间的 Python 代码:

## 蟒蛇 3

```
#import time
import time

# get data of 4 th april 2021  at time 9 pm
print(time.strptime('04/04/21 09:31:22', '%d/%m/%y %H:%M:%S'))

# get data of 5 th april 2021  at time 9 pm
print(time.strptime('05/04/21 09:00:42', '%d/%m/%y %H:%M:%S'))

# get data of 6 th april 2021  at time 9 pm
print(time.strptime('06/04/21 09:11:42', '%d/%m/%y %H:%M:%S'))

# get data of 7 th april 2021  at time 9 pm
print(time.strptime('07/04/21 09:41:12', '%d/%m/%y %H:%M:%S'))
```

**输出:**

> time.struct_time(tm_year=2021，tm_mon=4，tm_mday=4，tm_hour=9，tm_min=31，tm_sec=22，tm_wday=6，tm_yday=94，tm_isdst=-1)
> 
> time.struct_time(tm_year=2021，tm_mon=4，tm_mday=5，tm_hour=9，tm_min=0，tm_sec=42，tm_wday=0，tm_yday=95，tm_isdst=-1)
> 
> time.struct_time(tm_year=2021，tm_mon=4，tm_mday=6，tm_hour=9，tm_min=11，tm_sec=42，tm_wday=1，tm_yday=96，tm_isdst=-1)
> 
> time.struct_time(tm_year=2021，tm_mon=4，tm_mday=7，tm_hour=9，tm_min=41，tm_sec=12，tm_wday=2，tm_yday=97，tm_isdst=-1)

还可以以 yyyy-mm-dd datetime 格式获取字符串 datetime。yyyy-mm-dd 代表年-月-日。我们可以使用 strptime()函数将字符串格式转换为 DateTime。我们将使用“%Y/%m/%d”格式将字符串转换为日期时间。

> **语法：** datetime.datetime.strptime（输入，格式）
> 
> **参数:**
> 
> *   输入是字符串日期时间
> *   格式是格式–“yyyy-mm-DD”
> *   日期时间是模块

首先，导入模块并给出输入日期时间字符串。现在使用 strptime 获取所需的格式，并使用 date()函数从 DateTime 中获取日期

**示例 1** :将字符串日期时间格式转换为日期时间的 Python 程序

## 蟒蛇 3

```
# import the datetime module
import datetime

# datetime in string format for may 25 1999
input = '2021/05/25'

# format
format = '%Y/%m/%d'

# convert from string format to datetime format
datetime = datetime.datetime.strptime(input, format)

# get the date from the datetime using date()
# function
print(datetime.date())
```

**输出:**

> 2021-05-25

**示例 2:** 将字符串日期时间列表转换为日期时间

## 蟒蛇 3

```
# import the datetime module
import datetime

# datetime in string format for list of dates
input = ['2021/05/25', '2020/05/25', '2019/02/15', '1999/02/4']

# format
format = '%Y/%m/%d'
for i in input:

    # convert from string format to datetime format
    # and get the date
    print(datetime.datetime.strptime(i, format).date())
```

**输出:**

> 2021-05-25
> 
> 2020-05-25
> 
> 2019-02-15
> 
> 1999-02-04

我们也可以用**% d/% M/% Y % H:% M:% S”**格式显示日期时间。为此，我们将获取日期-月-年小时数:分钟的数据；秒格式。因此，我们必须获取输入日期时间字符串，并获得这种格式

> **语法:**datetime . strptime(input _ date，“%d/%m/%Y %H:%M:%S”)
> 
> **参数:**
> 
> *   日期时间是模块
> *   input_date 是字符串日期时间格式
> *   strptime 用于将 input_date 字符串转换为 datetime

**示例 3:** Python 程序将字符串日期时间转换为“%d/%m/%Y %H:%M:%S”格式

## 蟒蛇 3

```
#import datetime
from datetime import datetime

# consider the datetime string in dd/mm/yyyy
# hh:mm:ss format
date = "25/05/2021 02:35:15"

# convert string datetime to  dd/mm/yyyy hh:mm:ss
# format
datetime_date = datetime.strptime(date, "%d/%m/%Y %H:%M:%S")
print(datetime_date)
```

**输出:**

> 2021-05-25 02:35:15