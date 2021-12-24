# 将字符串转换为 Python 中带时区的日期时间

> 原文:[https://www . geesforgeks . org/convert-string-to-datetime-in-python-with-time zone/](https://www.geeksforgeeks.org/convert-string-to-datetime-in-python-with-timezone/)

**先决条件:** [日期时间模块](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

在本文中，我们将学习如何使用 Python 从时间字符串中获取 datetime 对象。

若要将时间字符串转换为 datetime 对象，请使用 datetime 模块的 datetime.strptime()函数。此函数返回 datetime 对象。

> **语法 ：** datetime.strptime（date_string， format）
> 
> **参数:**
> 
> *   **date_string** :包含需要哪个 datetime 对象的指定时间字符串。* *必需
> *   **格式**:date _ string 的缩写格式
> 
> **返回:**返回给定日期字符串的日期时间对象

可以传递给 strptime()的可接受格式列表:

<figure class="table">

| 指示的 | 意义 | 输出格式 |
| --- | --- | --- |
| %Y | 缩写的工作日名称。 | 珊，老兄，Sat |
| %m | 月是一个用零填充的十进制数。 | 01, 02, …, 12 |
| %b | 月作为区域设置的缩写名称。 | 一月，二月，…，十二月 |
| %d | 以零填充的十进制数表示的一个月中的某一天。 | 01, 02, …, 31 |
| %H | 小时(24 小时制)作为零填充十进制数。 | 00, 01, …, 23 |
| %I | 小时(12 小时制)作为零填充十进制数。 | 01, 02, …, 12 |
| %M | 分钟是一个用零填充的十进制数。 | 00, 01, …, 59 |
| %S | 第二个是用零填充的十进制数。 | 00, 01, …, 59 |
| %f | 微秒为十进制数，左边用零填充。 | 000000, 000001, …, 999999 |
| %p | 区域设置相当于上午或下午 | 上午，下午，上午，下午 |
| %z | HHMM 形式的世界协调时偏移量 | +0000, -0400, +0530 |

</figure>

**示例 1:** 将日期时间字符串转换为日期时间

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Getting datetime object using a date_string

# importing datetime module
import datetime

# datestring for which datetime_obj required
date_string = '2021-09-01 15:27:05.004573 +0530'
print("string datetime: ")
print(date_string)
print("datestring class is :", type(date_string))

# using strptime() to get datetime object
datetime_obj = datetime.datetime.strptime(
    date_string, '%Y-%m-%d %H:%M:%S.%f %z')

print("converted to datetime:")

# Printing datetime
print(datetime_obj)

# Checking class of datetime_obj.
print("datetime_obj class is :", type(datetime_obj))
```

**输出:**

```py
string datetime: 
2021-09-01 15:27:05.004573 +0530
datestring class is : <class 'str'>
converted to datetime:
2021-09-01 15:27:05.004573+05:30
datetime_obj class is : <class 'datetime.datetime'>
```

**示例 2:** 将日期时间字符串转换为日期时间

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Getting datetime object using a date_string

# importing datetime module
import datetime

# datestring for which datetime_obj required
date_string = '2021-09-01 15:27:05'

# using strptime() to get datetime object
datetime_obj = datetime.datetime.strptime(date_string, '%Y-%m-%d %H:%M:%S')

# Printing datetime
print(datetime_obj)
```

**输出:**

> 2021-09-01 15:27:05

在本例中，从第一个示例中删除了微秒和时区部分，因此我们还需要从格式字符串中删除微秒和时区缩写

**示例 3:** 将日期时间字符串转换为日期时间

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Getting datetime object using a date_string

# importing datetime module
import datetime

# datestring for which datetime_obj required
date_string = 'Sep 01 2021 03:27:05 PM'

# using strptime() to get datetime object
datetime_obj = datetime.datetime.strptime(date_string, '%b %d %Y %I:%M:%S %p')

# Printing datetime
print(datetime_obj)
```

**输出:**

> 2021-09-01 15:27:05