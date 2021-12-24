# 使用 Python 获取当前时间(单位为毫秒)

> 原文:[https://www . geesforgeks . org/get-current-time-in-毫秒-使用-python/](https://www.geeksforgeeks.org/get-current-time-in-milliseconds-using-python/)

**Python 中的时间模块**提供了各种与时间相关的功能。该模块属于 Python 的标准实用程序模块，因此无需从外部安装。

`time.time()`时间模块的方法用于获取自纪元以来的时间，单位为秒。闰秒的处理依赖于平台。

**注:**纪元是时间开始的点，与平台有关。在 Windows 和大多数 Unix 系统上，纪元是 1970 年 1 月 1 日 00:00:00(世界协调时)，闰秒不会计入自纪元以来的秒数。要查看给定平台上的纪元，我们可以使用`time.gmtime(0)`。

> **语法:** time.time()
> 
> **返回类型:**该方法返回一个浮点值，表示自纪元以来的时间(以秒为单位)。

**例 1:**

```py
# Python program to get
# time in milliseconds

# Import class time from time module
from time import time

# time() function is multiplied with 
# 1000 to convert seconds into milliseconds.
milliseconds = int(time() * 1000)

print("Time in milliseconds since epoch", milliseconds)
```

**输出:**

```py
Time in milliseconds since epoch 1576071104408

```

**示例 2:** 使用λ函数

```py
# Python program to get
# time in milliseconds

# Import class time from time module
from time import time

# Get time in milliseconds using
# lambda function
milliseconds = lambda: int(time() * 1000)

print("Time in milliseconds since epoch", milliseconds())
```

**输出:**

```py
Time in milliseconds since epoch 1576071316487

```