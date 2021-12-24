# 将“未知格式”字符串转换为 Python 中的日期时间对象

> 原文:[https://www . geesforgeks . org/convert-unknown-format-strings-to-datetime-objects-in-python/](https://www.geeksforgeeks.org/convert-unknown-format-strings-to-datetime-objects-in-python/)

在本文中，我们将看到如何在 Python 中将“未知格式”字符串转换为 DateTime 对象。

假设有两个字符串包含未知格式的日期，我们不知道该格式。这里我们只知道两个字符串都包含有效的日期时间表达式。通过使用包含日期解析器的 dateutil 模块，可以解析多种格式的日期字符串。

让我们看一些例子，从多方面说明这种转换:

### **示例 1:** 将“未知格式”字符串转换为日期时间对象

在下面的示例中，日期字符串“19750503T080120”的指定未知格式被解析为 DateTime 对象的有效已知格式。

## 蟒蛇 3

```
# Python3 code to illustrate the conversion of
# "unknown format" strings to DateTime objects

# Importing parser from the dateutil.parser
import dateutil.parser as parser

# Initializing an unknown format date string
date_string = "19750503T080120"

# Calling the parser to parse the above
# specified unformatted date string
# into a datetime objects
date_time = parser.parse(date_string)

# Printing the converted datetime object
print(date_time)
```

**输出:**

```
1975-05-03 08:01:20
```

### **示例 2:** 将当前日期和时间转换为日期时间对象

在下面的示例中，当前日期和时间已被解析为 datetime 对象。

## 蟒蛇 3

```
# Python3 code to illustrate the conversion of
# "unknown format" strings to DateTime objects

# Importing parser from the dateutil.parser and
# dt from datetime module
import dateutil.parser as parser
import datetime as dt

# Calling the now() function to
# return the current datetime
now = dt.datetime.now()

# Calling the isoformat() to return the
# current datetime in isoformat and print it
print(now.isoformat())

# Now calling the parser to parse the
# above returned isoformat datetime into
# a valid known format of datetime object
print(parser.parse(now.isoformat()))
```

**输出:**

```
2021-08-20T13:35:23.829488
2021-08-20 13:35:23.829488
```

有时日期时间字符串可能不明确，例如 01-02-2003 可能表示 1 月 2 日或 2 月 1 日。为了消除这种模糊性，我们有两个参数，如 dayfirst 和 yearfirst，如下例所示。

### **示例 3:** 将特定的未知格式转换为日期时间对象

在下面的示例中，指定的日期时间是“10-09-2021”。parse()将参数 dayfirst 用作 True，并将输出返回为“2021-09-10 00:00:00”，即 2021 年的 10 月 9 日。

## 蟒蛇 3

```
# Python3 code to illustrate the conversion of
# "unknown format" strings to DateTime objects

# Importing parser from the dateutil.parser
import dateutil.parser as parser

# Now parsing the "10-09-2021" datetime with
# dayfirst parameter
B = parser.parse("10-09-2021", dayfirst = True)

# Printing the parsed datetime
print(B)
```

**输出:**

```
2021-09-10 00:00:00
```