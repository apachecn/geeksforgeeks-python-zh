# 在 Python 中将日期字符串转换为时间戳

> 原文:[https://www . geesforgeks . org/convert-date-string-timestamp-in-python/](https://www.geeksforgeeks.org/convert-date-string-to-timestamp-in-python/)

我们用来将日期和时间存储到数据库中的最常见方式是以时间戳的形式。当我们在将日期和时间存储到数据库之前收到字符串形式的日期和时间时，我们会将该日期和时间字符串转换为时间戳。Python 提供了各种将日期转换为时间戳的方法。本文中讨论的几个问题是:

*   [使用 timetuple()](#timetuple)
*   [使用时间戳()](#timestamp)

#### 使用 timetuple()

**进场:**

*   导入日期时间用于导入日期和时间模块
*   导入日期时间模块后，下一步是接受日期字符串作为输入，然后将其存储到变量中
*   然后我们使用 strptime 方法。此方法采用两个参数:
    *   第一个参数是日期和时间的字符串格式
    *   第二个参数是输入字符串的格式
*   我们将日期和时间字符串转换为日期对象
*   然后我们使用 timetuple()将日期对象转换为元组
*   最后，我们使用 mktime(元组)将日期元组转换为时间戳。

**例 1:**

```py
# Python program to convert 
# date to timestamp

import time
import datetime

string = "20/01/2020"
print(time.mktime(datetime.datetime.strptime(string,
                                             "%d/%m/%Y").timetuple()))
```

**输出:**

```py
1579458600.0

```

**例 2:**

```py
# Python program to convert 
# date to timestamp

import time
import datetime

string = "20/01/2020"

element = datetime.datetime.strptime(string,"%d/%m/%Y")

tuple = element.timetuple()
timestamp = time.mktime(tuple)

print(timestamp)
```

**输出:**

```py
1579458600.0

```

#### 使用时间戳()

**进场:**

*   导入日期时间用于导入日期和时间模块
*   导入日期时间模块后，下一步是接受日期字符串作为输入，然后将其存储到变量中
*   然后我们使用 strptime 方法。这个方法有两个参数
    *   第一个参数是日期和时间的字符串格式
    *   第二个参数是输入字符串的格式
*   然后它以时间戳格式返回日期和时间值，我们将其存储在时间戳变量中。

**例 1:**

```py
# Python program to convert 
# date to timestamp

import time
import datetime

string = "20/01/2020"

element = datetime.datetime.strptime(string,"%d/%m/%Y")

timestamp = datetime.datetime.timestamp(element)
print(timestamp)
```

**输出:**

```py
1579458600.0

```