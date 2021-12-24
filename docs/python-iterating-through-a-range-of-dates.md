# Python–遍历一系列日期

> 原文:[https://www . geesforgeks . org/python-遍历日期范围/](https://www.geeksforgeeks.org/python-iterating-through-a-range-of-dates/)

在本文中，我们将讨论如何在一系列日期中迭代日期时间。

## **方法 1:使用循环和时间增量**

[时间增量](https://www.geeksforgeeks.org/python-datetime-timedelta-function/)用于获取日期，循环是从开始日期到结束日期迭代日期

**语法**:

```py
delta = datetime.timedelta(days=1)
while (start_date <= end_date):
    print(start_date)
    start_date += delta
```

### 示例:Python 代码，显示 2021 年 2 月 1 日 <sup>st</sup> 到 2021 年 3 月 1 日 <sup>st</sup> 的日期

## 蟒蛇 3

```py
# import datetime module
import datetime

# consider the start date as 2021-february 1 st
start_date = datetime.date(2021, 2, 1)

# consider the end date as 2021-march 1 st
end_date = datetime.date(2021, 3, 1)

# delta time
delta = datetime.timedelta(days=1)

# iterate over range of dates
while (start_date <= end_date):
    print(start_date, end="\n")
    start_date += delta
```

**输出**:

```py
2021-02-01
2021-02-02
2021-02-03
2021-02-04
2021-02-05
2021-02-06
2021-02-07
2021-02-08
2021-02-09
2021-02-10
2021-02-11
2021-02-12
2021-02-13
2021-02-14
2021-02-15
2021-02-16
2021-02-17
2021-02-18
2021-02-19
2021-02-20
2021-02-21
2021-02-22
2021-02-23
2021-02-24
2021-02-25
2021-02-26
2021-02-27
2021-02-28
2021-03-01
```

## 方法二:利用熊猫

我们可以使用熊猫中可用的 [date_range()](https://www.geeksforgeeks.org/python-pandas-date_range-method/) 函数方法。它用于返回固定频率的日期时间索引。

**语法**:

```py
pandas.date_range(start, end)
```

在哪里

*   开始是开始日期
*   结束是结束日期

我们可以使用 date()函数迭代获取日期。

### **例**:

## 蟒蛇 3

```py
# import pandas module
import pandas as pd

# specify the start date is 2021 jan 1 st
# specify the emd date is 2021 feb 1 st
a = pd.date_range(start='1/1/2021', end='2/1/2021')

# display only date using date() function
for i in a:
    print(i.date())
```

**输出**:

```py
2021-01-01
2021-01-02
2021-01-03
2021-01-04
2021-01-05
2021-01-06
2021-01-07
2021-01-08
2021-01-09
2021-01-10
2021-01-11
2021-01-12
2021-01-13
2021-01-14
2021-01-15
2021-01-16
2021-01-17
2021-01-18
2021-01-19
2021-01-20
2021-01-21
2021-01-22
2021-01-23
2021-01-24
2021-01-25
2021-01-26
2021-01-27
2021-01-28
2021-01-29
2021-01-30
2021-01-31
2021-02-01
```