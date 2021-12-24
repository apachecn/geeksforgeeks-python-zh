# 如何将一个 Python datetime.datetime 转换成 excel 日期序号

> 原文:[https://www . geesforgeks . org/如何转换-a-python-datetime-datetime-to-excel-serial-date-number/](https://www.geeksforgeeks.org/how-to-convert-a-python-datetime-datetime-to-excel-serial-date-number/)

本文将讨论 python datetime.datetime 到 excel 序列号的转换。Excel“序列日期”格式实际上是 1900-01-00 以来的天数。**[**str time()**](https://www.geeksforgeeks.org/python-strftime-function/)函数用于将日期和时间对象转换为它们的字符串表示。它接受一个或多个格式化代码输入，并返回字符串表示形式。**

> ****语法:****
> 
> **strftime（format）**
> 
>  ****参数:**该函数接受如下所示的参数:
> 
> *   **格式:**这是给定日期和时间对象将被表示的指定格式代码。
> 
> **返回值:**返回日期或时间对象的字符串表示形式。**

****示例 1:** 在下面的示例中，当前日期和时间正在转换为 excel 序列号。并且返回的输出将采用 Excel 接受的有效日期/时间格式‘08/23/21 15:15:53’，并允许在 Excel 中排序。**

## **蟒蛇 3**

```
# Python3 code to illustrate the conversion of
# datetime.datetime to excel serial date number

# Importing datetime module
import datetime

# Calling the now() function to return
# current date and time
current_datetime = datetime.datetime.now()

# Calling the strftime() function to convert
# the above current datetime into excel serial date number
print(current_datetime.strftime('%x %X'))
```

****输出:****

```
08/23/21 15:15:53
```

**如果我们需要日期值形式的 excel 序列号，那么可以使用 **toordinal()** 函数来完成。**

****示例 2:** 日期值形式的序列号**

## **蟒蛇 3**

```
# Python3 code to illustrate the conversion of
# datetime.datetime to excel serial date number

# Importing date module from datetime
from datetime import date

# Taking the parameter from the calling function
def convert_date_to_excel_ordinal(day, month, year):

    # Specifying offset value i.e.,
    # the date value for the date of 1900-01-00
    offset = 693594
    current = date(year, month, day)

    # Calling the toordinal() function to get
    # the excel serial date number in the form
    # of date values
    n = current.toordinal()
    return (n - offset)

# Calculating the excel serial date number
# for the date "02-02-2021" by calling the
# user defined function convert_date_to_excel_ordinal()
print(convert_date_to_excel_ordinal(2, 2, 2021))
```

****输出:****

```
44229
```

****示例:**在下面的示例中，“2021-05-04”日期正在参照 1899-12-30 日期转换为 excel 序列号。**

## **蟒蛇 3**

```
# Python3 code to illustrate the conversion of
# datetime.datetime to excel serial date number

# Importing datetime module
from datetime import datetime
import datetime as dt

def excel_date(date1):

    # Initializing a reference date
    # Note that here date is not 31st Dec but 30th!
    temp = dt.datetime(1899, 12, 30)
    delta = date1 - temp
    return float(delta.days) + (float(delta.seconds) / 86400)

# Calculating the excel serial date number
# for the date "2021-05-04" by calling the
# user defined function excel_date()
print(excel_date(datetime(2021, 2, 4)))
```

****输出:****

```
44231.0
```