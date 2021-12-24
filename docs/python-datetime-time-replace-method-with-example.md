# Python DateTime–time .用示例替换()方法

> 原文:[https://www . geesforgeks . org/python-datetime-time-replace-method-with-example/](https://www.geeksforgeeks.org/python-datetime-time-replace-method-with-example/)

在本文中，我们将讨论 Python 中的 time.replace()方法。此方法用于操作模块日期时间的时间类对象。它用于用相同的值替换时间，除了那些由任何关键字参数赋予新值的参数。

> **语法:**替换(年=自.年，月=自.月，日=自.日)
> 
> **参数:**
> 
> *   **年:**新年值(范围:1 < =年< = 9999)
> *   **月:**新月值(范围:1 < =月< = 12)
> *   **日:**新日值(范围:1 < =日< = 31)
> 
> **返回:**新的日期时间对象。

**Python 程序获取时间并显示:**

## 蟒蛇 3

```
# import time from datetime
from datetime import time

# create time
x = time(5,34,7,6789)
print("Time:", x)
```

**输出:**

```
Time: 05:34:07.006789
```

#### 示例 1: Python 程序替换给定时间的小时

## 蟒蛇 3

```
# import time from datetime
from datetime import time

# create time
x = time(5, 34, 7, 6789)

print("Actual Time:", x)

# replace hour from 5 to 10
final = x.replace(hour = 10)

print("New time after changing the hour:", final)
```

**输出:**

```
Actual Time: 05:34:07.006789
New time after changing the hour: 10:34:07.006789
```

#### 示例 2: Python 程序不时替换分钟

## 蟒蛇 3

```
# import time from datetime
from datetime import time

# create time
x = time(5, 34, 7, 6789)

print("Actual Time:", x)

# replace minute from 34 to 12
final = x.replace(minute = 12)

print("New time after changing the minute:", final)
```

**输出:**

```
Actual Time: 05:34:07.006789
New time after changing the minute: 05:12:07.006789
```

#### 示例 3:替换秒的 Python 代码

## 蟒蛇 3

```
# import time from datetime
from datetime import time

# create time
x = time(5,34,7,6789)

print("Actual Time:", x)

# replace second from 7 to 2
final = x.replace(second = 2)

print("New time after changing the second:", final)
```

**输出:**

```
Actual Time: 05:34:07.006789
New time after changing the second: 05:34:02.006789
```

#### 示例 4:一次全部替换的 Python 程序

## 蟒蛇 3

```
# import time from datetime
from datetime import time

# create time
x = time(5,34,7,6789)

print("Actual Time:", x)

# replace hour from 5 to 10
# replace minute from 34 to 11
# replace second from 7 to 1
# replace milli second from 6789 to 1234
final = x.replace(hour = 10, minute = 11,
                  second = 1, microsecond = 1234)

print("New time :", final)
```

**输出:**

```
Actual Time: 05:34:07.006789
New time : 10:11:01.001234
```