# Python |使用 datetime.timedelta()方法的两个日期之间的差异(以分钟为单位)

> 原文:[https://www . geesforgeks . org/python-分钟两个日期之间的差异-使用-datetime-timedelta-method/](https://www.geeksforgeeks.org/python-difference-between-two-dates-in-minutes-using-datetime-timedelta-method/)

要找出 Python 中两个日期之间的区别，可以使用**日期时间**库中的**时间增量**类。timedelta 类存储两个 datetime 对象之间的差异。
要以分钟的形式找到两个日期之间的差异，可以使用 timedelta 对象的属性**秒**，该属性可以进一步除以 60 转换为分钟。
**例 1:**
下面的程序取两个 datetime 对象，以分钟为单位找出它们之间的区别。

```
import datetime

# datetime(year, month, day, hour, minute, second)
a = datetime.datetime(2017, 6, 21, 18, 25, 30)
b = datetime.datetime(2017, 5, 16, 8, 21, 10)

# returns a timedelta object
c = a-b 
print('Difference: ', c)

minutes = c.total_seconds() / 60
print('Total difference in minutes: ', minutes)

# returns the difference of the time of the day
minutes = c.seconds / 60
print('Difference in minutes: ', minutes)
```

**输出:**

```
Difference:  36 days, 10:04:20
Difference in minutes:  604.3333333333334
```

**示例 2:**
要获得更合适的答案，可以使用 divmod()返回以秒为单位的分钟小数部分:

```
import datetime

# datetime(year, month, day, hour, minute, second)
a = datetime.datetime(2017, 6, 21, 18, 25, 30)
b = datetime.datetime(2017, 5, 16, 8, 21, 10)

# returns a timedelta object
c = a-b 
print('Difference: ', c)

# returns (minutes, seconds)
minutes = divmod(c.total_seconds(), 60) 
print('Total difference in minutes: ', minutes[0], 'minutes',
                                 minutes[1], 'seconds')

# returns the difference of the time of the day (minutes, seconds)
minutes = divmod(c.seconds, 60) 
print('Total difference in minutes: ', minutes[0], 'minutes',
                                 minutes[1], 'seconds')
```

**输出:**

```
Difference:  36 days, 10:04:20
Difference in minutes:  604 minutes 20 seconds
```