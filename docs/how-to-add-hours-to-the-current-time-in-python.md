# 如何在 Python 中给当前时间增加小时？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中向当前时间添加小时数/](https://www.geeksforgeeks.org/how-to-add-hours-to-the-current-time-in-python/)

**先决条件:** [日期时间模块](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

每一分钟都应该被享受和品味。时间是用小时、天、年等等来衡量的。时间帮助我们养成组织和安排日常活动的好习惯。在本文中，我们将看到如何从 python 模块中提取实时信息。有多种方法可以将日期和时间功能传递给程序。Python“时间”和“日历”模块有助于跟踪日期和时间。此外，“日期时间”提供了一个以简单和复杂的方式控制日期和时间的类。因此，在本模块的帮助下，我们将尝试在“timedelta()”的帮助下，通过实时增加小时数来计算出我们未来的期望时间。

获取当前日期和时间日期时间。使用了日期时间模块的 now()函数。该函数返回当前的本地日期和时间。

> **语法:** datetime.now(tz)
> 
> **参数:** tz:需要当前时间和日期的指定时区。(默认使用格林威治子午线时间。)
> 
> **返回:**以时间格式返回当前日期和时间。

**方法:**

*   Import the date time module.
*   Displays the current time.
*   Create a new variable until the update time.
*   Store the update time in this variable.
*   Show the update time.

**实施:**

**第一步:显示当前时间。**

首先，我们将从日期时间模块导入“日期时间”和“时间增量”，然后我们将我们的当前时间存储在一个变量中。之后，我们将以“HH:MM:SS”格式对齐日期。现在我们可以打印我们的现在时间。

## 蟒 3

```py
#importing datetime module for now()  
from datetime import datetime, timedelta  

# using now() to get present_time  
present_time = datetime.now()  

#time formatting
'{:%H:%M:%S}'.format(present_time)    

print("Present time at greenwich meridian is "
      ,end = "")  
print( present_time )
```