# Python 日期时间–日期类

> 原文:[https://www.geeksforgeeks.org/python-datetime-date-class/](https://www.geeksforgeeks.org/python-datetime-date-class/)

Date 类的对象表示根据当前公历包含年、月和日期的初始日期。这个日期可以双向无限期延长。第 1 年的 1 月 1 日称为第 1 天，1 月 2 日或第 2 年称为第 2 天，依此类推。

**语法:**

```py
class datetime.date(year, month, day)
```

参数必须在以下范围内–

*   MINYEAR(1) <= year <= MAXYEAR(9999)
*   1 <=月< = 12
*   1 <=天< =给定月份和年份中的天数

**注意:**如果参数不是整数，将引发类型错误，如果超出范围，将引发值错误。

**例:**

## 蟒 3

```py
# Python program to
# demonstrate date class

# import the date class
from datetime import date

# initializing constructor
# and passing arguments in the
# format year, month, date
my_date = date(2020, 12, 11)

print("Date passed as argument is", my_date)

# Uncommenting my_date = date(1996, 12, 39)
# will raise an ValueError as it is
# outside range

# uncommenting my_date = date('1996', 12, 11)
# will raise a TypeError as a string is
# passed instead of integer
```

**输出**

```py
Date passed as argument is 2020-12-11
```

## 类别属性

让我们看看这个类提供的属性–

<figure class="table">T26【月】

| 属性名 | 描述 |
| --- | --- |
| min | 最小可表示日期 |
| 最大可表示日期 | 最大可表示日期 |
| 分辨率 | 日期对象之间的最小可能差异 |
| 年份 | 年份的范围必须介于 MINYEAR 和 MAXYEAR 之间 |
| 的范围 |

</figure>

**示例 1:** 获取最小和最大可表示日期

T5】python 3T7

```py
from datetime import date

# Getting min date
mindate = date.min
print("Min Date supported", mindate)

# Getting max date
maxdate = date.max
print("Max Date supported", maxdate)
```

T8T10**输出**T1

**示例 2:** 从日期类

## 中访问年、月、日属性【python 3

```py
from datetime import date

# creating the date object
Date = date(2020, 12, 11)

# Accessing the attributes
print("Year:", Date.year)
print("Month:", Date.month)
print("Day:", Date.day)
```

**输出**

```py
Year: 2020
Month: 12
Day: 11
```