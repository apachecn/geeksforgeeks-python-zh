# Python |查找昨天、今天和明天的日期

> 原文:[https://www . geesforgeks . org/python-find-yesterdays-todays-and-tomorrow-date/](https://www.geeksforgeeks.org/python-find-yesterdays-todays-and-tomorrows-date/)

**先决条件:** [日期时间模块](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

我们可以通过导入模块`datetime`和`timedelta`来处理数据对象，以处理日期。

*   **Date and Time** module helps to find the current date by using `now()` or `today()` methods.
*   The **timedelta** class helps to find the date of the previous day and the date of the next day from the datetime module.

**时间增量语法:**

> class datetime.timedelta(天数=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)

[使用时间增量类](https://www.geeksforgeeks.org/python-datetime-module-with-examples/#timedelta)，因为用增量和减量直接操作日期会导致错误的日期。例如，如果当前日期是 12 月 31 日，则直接增加日期只会导致 12 月 32 日，这是错误的。如果我们想直接操作日期，我们首先检查日、月和年的组合，并相应地增加它们。但是，所有这些混乱可以通过使用 timedelta 类来控制。

**查找当前日期的语法:**

> datetime . now()
> 
> 返回:包含当前本地日期和时间的 datetime 对象。

**查找前一天和第二天日期的语法:**

> 前一天= datetime . now()-time delta(1)
> 
> 次日= datetime . now()+time delta(1)

**例:**

```py
# Python program to find yesterday,
# today and tomorrow

# Import datetime and timedelta
# class from datetime module
from datetime import datetime, timedelta

# Get today's date
presentday = datetime.now() # or presentday = datetime.today()

# Get Yesterday
yesterday = presentday - timedelta(1)

# Get Tomorrow
tomorrow = presentday + timedelta(1)

# strftime() is to format date according to
# the need by converting them to string
print("Yesterday = ", yesterday.strftime('%d-%m-%Y'))
print("Today = ", presentday.strftime('%d-%m-%Y'))
print("Tomorrow = ", tomorrow.strftime('%d-%m-%Y'))
```

**输出**

```py
Yesterday =  10-12-2019
Today =  11-12-2019
Tomorrow =  12-12-2019

```