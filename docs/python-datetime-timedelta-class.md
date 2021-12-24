# Python 日期时间–时间增量类

> 原文:[https://www . geesforgeks . org/python-datetime-time delta-class/](https://www.geeksforgeeks.org/python-datetime-timedelta-class/)

**时间增量**类用于计算日期之间的差异，代表一个持续时间。这种差异既可以是积极的，也可以是消极的。

**语法:**

> class datetime.timedelta(天数=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)

**示例:**

## 蟒蛇 3

```
# Timedelta function demonstration

from datetime import datetime, timedelta

# creating datetime objects
date1 = datetime(2020, 1, 3)
date2 = datetime(2020, 2, 3)

# difference between dates
diff = date2 - date1
print("Difference in dates:", diff)

# Adding days to date1
date1 += timedelta(days = 4)
print("Date1 after 4 days:", date1)

# Sutracting days from date1
date1 -= timedelta(15)
print("Date1 before 15 days:", date1)
```

**Output**

```
Difference in dates: 31 days, 0:00:00
Date1 after 4 days: 2020-01-07 00:00:00
Date1 before 15 days: 2019-12-23 00:00:00
```

## 类别属性:

让我们看看这个类提供的属性–

<figure class="table">

| 属性名 | 描述 |
| --- | --- |
| 部 | 时间增量对象的最小值是-999999999 |
| 最大 | timedelta 对象的最大值是 999999999 |
| 解决 | 时间增量对象之间的最小可能差异 |

</figure>

**示例:**获取时间增量对象的最小值和最大值

## 蟒蛇 3

```
from datetime import timedelta

# Getting minimum value
Min = timedelta.min
print("Minimum value of timedelta object", Min)

# Getting minimum value
Max = timedelta.max
print("Maximum value of timedelta object", Max)
```

**Output**

```
Minimum value of timedelta object -999999999 days, 0:00:00
Maximum value of timedelta object 999999999 days, 23:59:59.999999
```

**输出**

> 时间增量对象的最小值-999999999 天，0:00:00
> 
> 时间增量对象的最大值 99999999 天，23:59:59.999999

## 类函数

时间增量类只提供一个函数 **total_seconds()。**该方法返回 timedelta 对象提供的持续时间，以秒为单位。

**注:**持续时间超过 270 年，该方法精确到微秒。

**示例:**以秒为单位获取各种持续时间

## 蟒蛇 3

```
from datetime import timedelta

# Getting minimum value
obj = timedelta(hours=1)
print(obj.total_seconds())

obj = timedelta(minutes=1)
print(obj.total_seconds())

obj = timedelta(days=1)
print(obj.total_seconds())
```

**Output**

```
3600.0
60.0
86400.0
```

## 时间增量类支持的操作

<figure class="table">

| 操作员 | 描述 |
| --- | --- |
| 加法(+) | 添加并返回两个时间增量对象 |
| 减法(-) | 减去并返回两个时间增量对象 |
| 乘法(*) | 将时间增量对象乘以浮点或整数 |
| 分部(/) | 用浮点数或整数除 timedelta 对象 |
| 楼层划分(//) | 用 float 或 int 除 timedelta 对象，并返回输出的整数值 |
| 模(%) | 将两个时间增量对象相除，并返回余数 |
| +(小时增量) | 返回相同的时间增量对象 |
| -每小时一次 | 返回-1 *时间增量的结果 |
| abs(时间差) | 如果时间增量天数> 1=0，则返回+(时间增量)，否则返回-(时间增量) |
| str(时间差) | 返回一个格式为(+/-)天的字符串，HH:MM:SS。UUUUUU |
| rep(小时增量) | 返回构造函数调用形式的字符串表示形式 |

</figure>

**示例 1:** 对时间增量对象执行基本算术运算。

## 蟒蛇 3

```
from datetime import timedelta

# creating the timedelta object
t1 = timedelta(days=1)
print("Original timedelta:", t1)

# multiplication
t2 = t1*5.5
print("After Multiplication:", t2)

# Subtraction
res = t2 - t1
print("After Subtraction:", res)

# addition
res += t2
print("After Addition:", res)

# division
res = t2/2.5
print("After division:", res)

# floor division
res = t2 //2
print("After floor division:", res)

# Modulo
res = t2%timedelta(days=3)
print("After Modulo:", res)
```

**Output**

```
Original timedelta: 1 day, 0:00:00
After Multiplication: 5 days, 12:00:00
After Subtraction: 4 days, 12:00:00
After Addition: 10 days, 0:00:00
After division: 2 days, 4:48:00
After floor division: 2 days, 18:00:00
After Modulo: 2 days, 12:00:00
```

**示例 2:** 获取时间增量对象的绝对值和字符串表示

## 蟒蛇 3

```
from datetime import timedelta

# creating the timedelta object
t1 = timedelta(days=1)
print("Original timedelta:", t1)

# Negatiob of timedelta object
t1 = -(t1)
print("After Negation:", t1)

# Getting Absolute value
t1 = abs(t1)
print("Absolute Value:", t1)

# Getting string representation
print("String representation:", str(t1))

# Getting Constructor call
print("Constructor call:", repr(t1))
```

**Output**

```
Original timedelta: 1 day, 0:00:00
After Negation: -1 day, 0:00:00
Absolute Value: 1 day, 0:00:00
String representation: 1 day, 0:00:00
Constructor call: datetime.timedelta(1)
```

**注:**关于 Python Datetime 的更多信息，请参考 [Python Datetime 教程](https://www.geeksforgeeks.org/python-datetime-module/)