# 如何在 Python 中使用毫秒级的 str time

> 原文:[https://www . geeksforgeeks . org/如何使用-python 中带毫秒的 str time/](https://www.geeksforgeeks.org/how-to-use-strptime-with-milliseconds-in-python/)

**python 中的 strptime()** 函数将字符串转换为 DateTime 对象。strptime()是一个采用两个参数的类方法:

*   应该转换为 datetime 对象的字符串
*   用于分析字符串的格式字符串。

这两个字符串参数是将字符串转换为 DateTime 对象所必需的。

**语法:**

> stroptime(date _ string，format_string)

**格式代码列表:**

<figure class="table">

| **格式字符串** | **解读** | **例** |
| --- | --- | --- |
| %a | Weekday 作为缩写名称。 | 珊，老兄，Sat |
| %A | 全名为 Weekday。 | 星期天，星期一，…，星期六 |
| %w | Weekday 为十进制数，0 为星期日，6 为星期六。 | 0, 1, …, 6 |
| %d | 以零填充的十进制数表示的一个月中的某一天。 | 01, 02, …, 31 |
| %b | 月作为缩写名称。 | 一月，二月，…，十二月 |
| %B | 月份。 | 一月，二月，…，十二月 |
| %m | 月 | 01, 02, …, 12 |
| %y | 没有世纪的一年。 | 00, 01, …, 99 |
| %Y | 世纪之交。 | 0001, 0002, …, 2013, 2014, …, 9998, 9999 |
| %H | 小时(24 小时制)。 | 00, 01, …, 23 |
| %I | 小时(12 小时制)。 | 01, 02, …, 12 |
| %p | 上午或下午。 | 上午，下午 |
| %M | 分钟。 | 00, 01, …, 59 |
| %S | 其次。 | 00, 01, …, 59 |
| %f | 微秒为十进制数。 | 000000, 000001, …, 999999 |
| %z | HHMM[SS []形式的世界协调时偏移量。ffffff]]。 | +0000, -0400, +1030, +063415, -030712.345216 |
| %Z | 时区(世界协调时，格林尼治时间) |   |
| %j | 一年中的某一天。 | 001, 002, …, 366 |
| %U | 一年中的周数(周日是一周的第一天)。 | 00, 01, …, 53 |
| %W | 一年中的周数(星期一为一周的第一天)为十进制数。 | 00, 01, …, 53 |
| %c | 首选日期和时间表示。 | 1998 年 8 月 16 日 21:30 |
| %x | 首选日期表示。 | 08/16/8808/16/1998 |
| %X | 首选时间表示。 | 21:30:00**% %–**一个文字“%”字符。 |

</figure>

要用这个函数产生毫秒，在 python 中%f 是用在格式化代码中的。

下面给出了一些实现。

**示例 1:** 时间(毫秒)

## 蟒蛇 3

```py
from datetime import datetime

datetime_string = "15/06/2021 13:30:15.120"

print(type(datetime_string))

format = "%d/%m/%Y %H:%M:%S.%f"

# converting datetime string to datetime 
# object with milliseconds..
date_object = datetime.strptime(datetime_string, format)

print("date_object =", date_object)

# Type is datetime object
print(type(date_object))
```

**输出:**

```py
<class 'str'>
date_object = 2021-06-15 13:30:15.120000
<class 'datetime.datetime'>
```

**示例 2:** 毫秒时间

## 蟒蛇 3

```py
from datetime import datetime

# Getting current datetime and converting
# it to string
date_str = str(datetime.now())

print(type(date_str))

print(datetime.strptime(date_str, '%Y-%m-%d %H:%M:%S.%f'))
```

**输出:**

```py
<class 'str'>
2021-08-01 15:27:59.979673
```

**示例 3:** 毫秒时间

## 蟒蛇 3

```py
from datetime import datetime

# Using strptime() with milliseconds

date_time = datetime.strptime(
    "17 Oct 2021 15:48:35.525001", "%d %b %Y %H:%M:%S.%f")

print(date_time)
```

**输出:**

```py
2021-10-17 15:48:35.525001
```