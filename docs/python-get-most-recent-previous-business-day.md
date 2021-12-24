# Python–获取最近的前一个工作日

> 原文:[https://www . geesforgeks . org/python-get-最近-以前-工作日/](https://www.geeksforgeeks.org/python-get-most-recent-previous-business-day/)

给定一个日期，任务是编写一个 Python 程序来获取给定日期的最近一个工作日。

**示例:**

> **输入:** test_date = datetime(2020，1，31)
> 
> **产量:** 2020-01-30 00:00:00
> 
> **说明:【2020 年 1 月 31 日，为周五，最后一个工作日为周四，即 1 月 30 日。**
> 
> **输入:** test_date = datetime(2020，2，3)
> 
> **产量:** 2020-01-31 00:00:00
> 
> **说明:【2020 年 2 月 3 日，为周一，最后一个工作日为周五，即 1 月 31 日。**

**方法一:使用** [**时间增量()**](https://www.geeksforgeeks.org/python-datetime-timedelta-function/) **+工作日()**

在这种情况下，我们在星期一执行减去 3 的任务，在星期天执行减去 2 的任务，在所有其他日子执行减去 1 的任务。timedelta()执行减法任务，条件语句检查工作日。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Last business day
# using timedelta() + conditional statements + weekday()
from datetime import datetime, timedelta

# initializing dates
test_date = datetime(2020, 1, 31)

# printing original date
print("The original date is : " + str(test_date))

# getting difference
diff = 1
if test_date.weekday() == 0:
    diff = 3
elif test_date.weekday() == 6:
    diff = 2
else :
    diff = 1

# subtracting diff 
res = test_date - timedelta(days=diff)

# printing result
print("Last business day : " + str(res))
```

**输出:**

```
The original date is : 2020-01-31 00:00:00
Last business day : 2020-01-30 00:00:00
```

**方法二:使用** [**max()**](https://www.geeksforgeeks.org/python-max-function/) **+ %运算符+**[**time delta()**](https://www.geeksforgeeks.org/python-datetime-timedelta-function/)

**以类似的方式执行任务，唯一的区别是计算差异变化的方法，以获得 max()和%运算符。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of
# Last business day
# using max() + % operator + timedelta() 
from datetime import datetime, timedelta

# initializing dates
test_date = datetime(2020, 1, 31)

# printing original date
print("The original date is : " + str(test_date))

# getting difference
# using max() to get differences 
diff = max(1, (test_date.weekday() + 6) % 7 - 3)

# subtracting diff 
res = test_date - timedelta(days=diff)

# printing result
print("Last business day : " + str(res))
```

****输出:****

```
The original date is : 2020-01-31 00:00:00
Last business day : 2020-01-30 00:00:00
```

****方法 3:使用**[**PD . tseries . offset . business day(n)**](https://www.geeksforgeeks.org/python-pandas-tseries-offsets-businessday/)**

**在这种情况下，我们创建一个 1 天的工作日偏移量，并从初始化日期中减去。这将根据需要返回前一个工作日。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of
# Last business day
# using pd.tseries.offsets.BusinessDay(n)
import pandas as pd
from datetime import datetime

# initializing dates
test_date = datetime(2020, 2, 3)

# printing original date
print("The original date is : " + str(test_date))

# Creating Timestamp
ts = pd.Timestamp(str(test_date))

# Create an offset of 1 Business days
offset = pd.tseries.offsets.BusinessDay(n=1)

# getting result by subtracting offset
res = test_date - offset

# printing result
print("Last business day : " + str(res))
```

****输出:****

```
The original date is : 2020-02-03 00:00:00
Last business day : 2020-01-31 00:00:00
```