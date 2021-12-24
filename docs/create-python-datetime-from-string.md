# 从字符串

创建 Python 日期时间

> 原文:[https://www . geesforgeks . org/create-python-datetime-from-string/](https://www.geeksforgeeks.org/create-python-datetime-from-string/)

在本文中，我们将看到如何从给定的字符串创建 python DateTime 对象。

为此，我们将使用 **datetime.strptime()** 方法。strptime()方法返回一个与 date_string 对应的 DateTime 对象，该对象根据用户给出的格式字符串进行解析。

> **语法** ： datetime.strptime（date_string， format）

## 使用 strptime()将字符串转换为 DateTime

在这里，我们将把一个简单的字符串转换成 datetime 对象，为此，我们将把该字符串传递给 strptime()，并通过它来对象化 datetime 对象。

## 蟒蛇 3

```
from datetime import datetime

input_str = '21/01/24 11:04:19'

dt_object = datetime.strptime(
  input_str, '%d/%m/%y %H:%M:%S')

print("The type of the input date string now is: ", 
      type(dt_object))

print("The date is", dt_object)
```

**输出:**

> 现在输入日期字符串的类型是:<class></class>
> 
> 日期是 2024-01-21 11:04:19

## 使用 strptime()将包含单词的字符串转换为日期时间

strptime()方法也允许您将“单词”中的时间戳转换为日期时间对象。下面的代码片段显示了这是可以做到的:

## 蟒蛇 3

```
from datetime import datetime

time_str = 'May 17 2019  11:33PM'
dt_object = datetime.strptime(
  time_str, '%b %d %Y %I:%M%p')

print(dt_object)
```

**输出:**

```
2019-05-17 23:33:00
```

## python stroptime()value error

给定字符串的日期时间格式必须是已知的，否则会导致不必要的问题和错误。下面的代码片段显示了可能导致的问题:

## 蟒蛇 3

```
from datetime import datetime

time_str = '201123101455'

dt_obj = datetime.strptime(time_str, '%y%m%d%H%M%S')
dt_obj2 = datetime.strptime(time_str, '%d%m%y%H%S%M')

print ("1st interpretation of date from string is: ",dt_obj) 
print ("2nd interpretation of date from same string is", dt_obj2)
```

**输出:**

> 字符串日期的第一个解释是:2020-11-23 10:14:55
> 
> 同一字符串的第二次日期解释是 2023-11-20 10:55:14

如果字符串参数与格式参数不一致，strptime()方法将不起作用。以下代码片段显示了由于格式说明符不匹配而发生的错误。

## 蟒蛇 3

```
from datetime import datetime

time_str = '220917 114519'
dt_obj = datetime.strptime(time_str, '%d/%m/%y %H:%M:%S')

print ("The type is", type(dt_obj))
print ("The date is", date_time_obj)
```

**输出:**

> ValueError("时间数据%r 与格式%r 不匹配" %(data_string，format))

## 格式代码列表

格式说明符大多与 strftime()方法相同。这些说明符是:

<figure class="table">

| 指令 | 意义 | 例子 |
| --- | --- | --- |
| %a | 缩写的工作日名称。 | 珊，我的… |
| %A | 完整的工作日名称。 | 星期天，星期一，… |
| %w | 以十进制数表示的工作日。 | 0, 1, …, 6 |
| %d | 以零填充的十进制表示的月份中的某一天。 | 01, 02, …, 31 |
| %-d | 以十进制数表示的一个月中的某一天。 | 1, 2, …, 30 |
| %b | 缩写的月份名称。 | 一月，二月，…，十二月 |
| %B | 完整的月份名称。 | 一月，二月，… |
| %m | 月是一个用零填充的十进制数。 | 01, 02, …, 12 |
| %-m | 以十进制数表示的月份。 | 1, 2, …, 12 |
| %y | 没有世纪的年份作为零填充的十进制数。 | 00, 01, …, 99 |
| %-y | 没有世纪作为十进制数的年份。 | 0, 1, …, 99 |
| %y | 以世纪为十进制数的年份。 | 2013 年、2019 年等。 |
| %H | 小时(24 小时制)作为零填充十进制数。 | 00, 01, …, 23 |
| %-H | 小时(24 小时制)作为十进制数。 | 0, 1, …, 23 |
| %I | 小时(12 小时制)作为零填充十进制数。 | 01, 02, …, 12 |
| %-我 | 小时(12 小时制)作为十进制数。 | 1, 2, … 12 |
| %p | 区域设置的上午或下午。 | 上午，下午 |
| %M | 分钟是一个用零填充的十进制数。 | 00, 01, …, 59 |
| %-M | 分钟作为十进制数。 | 0, 1, …, 59 |
| %S | 第二个是用零填充的十进制数。 | 00, 01, …, 59 |
| %-S | 第二个十进制数。 | 0, 1, …, 59 |
| %f | 微秒为十进制数，左边用零填充。 | 000000 – 999999 |
| %z | 以+HHMM 或-HHMM 形式表示的世界协调时偏移量。 |   |
| %Z | 时区名称。 |   |
| %j | 以零填充的十进制数表示的一年中的某一天。 | 001, 002, …, 366 |
| %-j | 以十进制数表示的一年中的某一天。 | 1, 2, …, 366 |
| %U | 一年中的周数(周日是一周的第一天)。新年第一个星期日之前的所有日子都被认为是第 0 周。 | 00, 01, …, 53 |
| %W | 一年中的周数(星期一是一周的第一天)。新年第一个星期一之前的所有日子都被认为是在第 0 周。 | 00, 01, …, 53 |
| %c | 区域设置的适当日期和时间表示。 | 2013 年 9 月 30 日 07:06:05 |
| %x | 区域设置的适当日期表示。 | 09/30/13 |
| %% | 文字“%”字符。 | %
 |

</figure>