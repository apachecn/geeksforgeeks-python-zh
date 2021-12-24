# 如何在 Python 中给日期添加天数？

> 原文:[https://www . geesforgeks . org/如何在 python 中添加日期天数/](https://www.geeksforgeeks.org/how-to-add-days-to-a-date-in-python/)

Python 提供了一个内置模块 **datetime** ，允许轻松操作和修改日期和时间值。它允许算术运算以及格式化从日期时间模块获得的输出。该模块包含各种类，如日期、时间、时间增量等。模拟日期和时间(月、年和日)的简单实现。

日期和时间对象是使用日期时间模块创建的，该模块是不可变的并且是可散列的。在 python 中，DateTime 模块的以下类用于向日期添加日期:

1.  **日期时间–**日期时间对象以小时、分钟、秒为单位给出日期和时间。日期时间库提供对日期和时间对象(月、日、年、秒和微秒)的组合的操作。
2.  **时间增量**–时间增量类别代表持续时间。DateTime 库提供了 timedelta 方法来执行与日期相关的操作，并计算时间对象的差异。它主要用于执行算术运算，如加法、减法和乘法。通过指定 days 属性值，我们可以向指定的日期添加天数。

> **语法:** datetime.timedelta(天=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)

**示例 1:** 下面的 Python 代码用于在 Python 中给日期添加日期

## 蟒蛇 3

```py
from datetime import datetime
from datetime import timedelta

# taking input as the date
Begindatestring = "2020-10-11"

# carry out conversion between string 
# to datetime object
Begindate = datetime.strptime(Begindatestring, "%Y-%m-%d")

# print begin date
print("Beginning date")
print(Begindate)

# calculating end date by adding 10 days
Enddate = Begindate + timedelta(days=10)

# printing end date
print("Ending date")
print(Enddate)
```

**输出:**

```py
Beginning date
2020-10-11 00:00:00
Ending date
2020-10-21 00:00:00
```

**示例 2:** 程序以 yyyy-mm-dd 格式向开始日期添加 10 天

## 蟒蛇 3

```py
from datetime import datetime
from datetime import timedelta
from datetime import date

# taking input as the current date
# today() method is supported by date 
# class in datetime module
Begindatestring = date.today()

# print begin date
print("Beginning date")
print(Begindatestring)

# calculating end date by adding 4 days
Enddate = Begindatestring + timedelta(days=4)

# printing end date
print("Ending date")
print(Enddate)
```

**输出:**

```py
Beginning date
2020-12-05
Ending date
2020-12-09
```