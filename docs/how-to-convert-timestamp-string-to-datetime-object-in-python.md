# 如何在 Python 中将时间戳字符串转换为 datetime 对象？

> 原文:[https://www . geesforgeks . org/如何在 python 中将时间戳字符串转换为日期时间对象/](https://www.geeksforgeeks.org/how-to-convert-timestamp-string-to-datetime-object-in-python/)

Python 有一个名为 [DateTime](https://www.geeksforgeeks.org/python-datetime-module-with-examples/) 的模块来处理日期和时间。我们不需要单独安装它。它是用 python 包本身预安装的。UNIX 时间戳是特定日期和 1970 年 1 月 1 日(世界协调时)之间的几秒钟。

## DateTime 对象的时间戳

您可以简单地使用 DateTime 模块中的 **fromtimestamp** 函数从 UNIX 时间戳中获取日期。该函数将时间戳作为输入，并将相应的 DateTime 对象返回给时间戳。

**语法:**

```py
fromtimestamp(timestamp, tz=None)
```

**示例:** Python 时间戳到日期时间

## 蟒蛇 3

```py
from datetime import datetime

timestamp = 1545730073
dt_obj = datetime.fromtimestamp(1140825600)

print("date_time:",dt_obj)
print("type of dt:",type(dt_obj))
```

**输出:**

```py
date_time: 2006-02-25 05:30:00
type of dt_obj: <class 'datetime.datetime'>

```

这里，我们已经从 DateTime 模块导入了 DateTime 类。然后我们使用了*datetime . frontimestamp()*类方法，返回本地 DateTime。

要获取特定形式的日期时间，可以使用**str time**函数。 [strftime()](https://www.geeksforgeeks.org/python-strftime-function/) 函数用于将日期和时间对象转换为它们的字符串表示。它接受一个或多个格式化代码输入，并返回字符串表示形式。

**示例:**

## 蟒蛇 3

```py
from datetime import datetime

timestamp = 1553367060
dt_obj = datetime.fromtimestamp(timestamp).strftime('%d-%m-%y')

print("date:",dt_obj)
```

**输出:**

```py
date: 24-03-19

```