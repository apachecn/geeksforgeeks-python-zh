# 如何在 Python 中把日期时间转换成日期

> 原文:[https://www . geesforgeks . org/如何用 python 将日期时间转换为日期时间/](https://www.geeksforgeeks.org/how-to-convert-datetime-to-date-in-python/)

在本文中，我们将看到如何在 Python 中将日期时间转换为日期。为此，我们将使用 strptime()方法。此方法用于从字符串创建日期时间对象。然后我们将使用 date()函数从 DateTime 对象中提取日期。

> **语法：** datetime.strptime（）
> 
> **参数:**
> 
> *   **参数:**可以是整数、浮点、元组、序列、数据帧，转换为日期时间作为其数据类型
> *   **格式:**这将是字符串，但默认为无。解析时间，例如“%d/%m/%Y”，请注意“%f”将一直解析到纳秒。

**示例 1:** 将日期时间转换为日期。

在这个例子中，我们创建了一个日期时间字符串，它的格式是**% d % b % Y % H % M % S】。**

## 蟒蛇 3

```py
# import important module
import datetime
from datetime import datetime

# Create datetime string
datetime_str = "24AUG2001101010"
print("datetime string : {}".format(datetime_str))

# call datetime.strptime to convert
# it into datetime datatype
datetime_obj = datetime.strptime(datetime_str, 
                                 "%d%b%Y%H%M%S")

# It will print the datetime object
print(datetime_obj)

# extract the time from datetime_obj
date = datetime_obj.date()
print(date)
```

**输出:**

```py
datetime string : 24AUG2001101010
2001-08-24 10:10:10
2001-08-24
```

**示例 2:** 将日期时间转换为数字日期。

在这个例子中，我们创建了一个日期时间字符串，它是**“100201095407”**，它的格式是**% d % M % y % H % M % S”**。

## 蟒蛇 3

```py
# import important module
import datetime
from datetime import datetime

# Create datetime string
datetime_str = "100201095407"
print("datetime string : {}".format(datetime_str))

# call datetime.strptime to convert
# it into datetime datatype
datetime_obj = datetime.strptime(datetime_str,
                                 "%d%m%y%H%M%S")

# It will print the datetime object
print(datetime_obj)

# extract the time from datetime_obj
date = datetime_obj.date()

# it will print date that we have
# extracted from datetime obj
print(date)
```

**输出**:

```py
datetime string : 100201095407
2001-02-10 09:54:07
2001-02-10
```

**例 3:** 用当前日期转换日期时间。

在这个例子中，我们获取当前的日期和时间，并从对象中提取它的日期。

## 蟒蛇 3

```py
# import important module
from datetime import datetime

# call datetime.strptime to
# convert it into datetime datatype
datetime_obj = datetime.now()

# It will print the datetime object
print(datetime_obj)

# extract the time from datetime_obj
date = datetime_obj.date()
print(date) 
```

**输出:**

```py
2021-08-07 06:30:20.227879
2021-08-07
```