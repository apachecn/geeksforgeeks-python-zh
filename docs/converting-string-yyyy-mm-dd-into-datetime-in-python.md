# 在 Python 中将字符串‘yyyy-mm-DD’转换为 DateTime

> 原文:[https://www . geesforgeks . org/converting-string-yyyy-mm-DD-to-datetime-in-python/](https://www.geeksforgeeks.org/converting-string-yyyy-mm-dd-into-datetime-in-python/)

在本文中，我们将使用 Python 将格式为“yyyy-mm-dd”的日期时间字符串转换为日期时间。

> yyyy-mm-dd 代表年-月-日。

我们可以使用 strptime()函数将字符串格式转换为日期时间。我们将使用“%Y/%m/%d”格式将字符串转换为日期时间。

> **语法:**
> 
> datetime.datetime.strptime（input，format）
> 
> **参数:**
> 
> *   输入是字符串日期时间
> *   格式是格式–“yyyy-mm-DD”
> *   日期时间是模块

**示例:**将字符串日期时间格式转换为日期时间的 Python 程序

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

**Output**

```
2021-05-25

```

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

**Output**

```
2021-05-25
2020-05-25
2019-02-15
1999-02-04

```