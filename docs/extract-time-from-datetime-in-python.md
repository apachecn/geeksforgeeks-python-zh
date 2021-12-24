# 从 Python 中的日期时间中提取时间

> 原文:[https://www . geesforgeks . org/extract-time-from-datetime-in-python/](https://www.geeksforgeeks.org/extract-time-from-datetime-in-python/)

在本文中，我们将看到如何在 Python 中从 DateTime 中提取时间。

在 Python 中，没有日期时间这样的数据类型，首先，我们必须将数据创建为日期时间格式，然后将日期时间数据转换为时间。Python 模块用于将数据转换为日期时间格式，但是在本文中，我们将使用日期时间模块来完成这项任务。

> **语法：** datetime.strptime（）
> 
> **参数:**
> 
> *   arg:它可以是整数、浮点、元组、序列、数据帧，以转换为日期时间作为其数据类型
> *   格式:这将是字符串，但默认为无。解析时间，例如“%d/%m/%Y”，请注意“%f”将一直解析到纳秒。
> 
> 例如–> format = " % Y % b % d % H % M % S "
> 
> 例如，datetime _ obj = datetime . strptime(" 19022002101010 "，%d%m%Y%H%M%S") #它将返回 datetime 对象。

## 从日期时间对象中提取时间

在本节中，我们将从 DateTime 对象中提取时间。

我们将字符串变成日期时间对象，现在我们通过调用**从日期时间对象中提取时间。time()** 法。

> **语法:**。时间()
> 
> **返回:**它将从日期时间对象返回时间

**下面是实现:**

## 蟒蛇 3

```
# import important module
import datetime
from datetime import datetime

# Create datetime string
datetime_str = "24AUG2001101010"

# call datetime.strptime to convert
# it into datetime datatype
datetime_obj = datetime.strptime(datetime_str, 
                                 "%d%b%Y%H%M%S")

# It will print the datetime object
print(datetime_obj)

# extract the time from datetime_obj
time = datetime_obj.time()

# it will print time that 
# we have extracted from datetime obj
print(time) 
```

**输出:**

```
2001-08-24 10:10:10
10:10:10
```

## 从时间中提取小时

在本节中，我们将从 DateTime 对象中提取提取的时间中提取小时，所有 3 个步骤与上一个示例相同。从 DateTime 对象中提取小时的 hour 方法。

我们必须提取时间，所以下一部分是通过调用。小时法。

> **语法:**。小时
> 
> **返回**:从时间戳返回小时。

**下面是实现:**

## 蟒蛇 3

```
# import important module
import datetime
from datetime import datetime

# Create datetime string
datetime_str = "31OCT2020231032"

# call datetime.strptime to convert
# it into datetime datatype
datetime_obj = datetime.strptime(datetime_str, "%d%b%Y%H%M%S")

# It will print the datetime object
print("date time : {}".format(datetime_obj))

# extract the time from datetime_obj
time = datetime_obj.time()

# it will print time that
# we have extracted from datetime obj
print("Time : {}".format(time)) 

# extract hour from time
hour = time.hour
print("Hour : {}".format(hour))
```

**输出:**

```
date time : 2020-10-31 23:10:32
Time : 23:10:32
Hour : 23
```

## 从时间中提取分钟和秒

在本例中，我们将添加。等一下。从 DateTime 对象中提取分钟和秒的第二种方法。

## 蟒蛇 3

```
# import important module
import datetime
from datetime import datetime

# Create datetime string
datetime_str = "10JAN300123000"

# call datetime.strptime to
# convert it into datetime datatype
datetime_obj = datetime.strptime(datetime_str,
                                 "%d%b%Y%H%M%S")

# It will print the datetime object
print("date time : {}".format(datetime_obj))

# extract the time from datetime_obj
time = datetime_obj.time()

# it will print time that we
# have extracted from datetime obj
print("Time : {}".format(time)) 

# extract minute from time
minute = time.minute
print("Minute : {}".format(minute))

# extract second from time
second = time.second
print("Second : {}".format(second))
```

**输出**:

```
date time : 3001-01-10 23:00:00
Time : 23:00:00
Minute : 0
Second : 0
```

## 如果日期备注在范围内，则确定时间

如果日期不在这个范围内，那么代码会给我们一个‘值错误’。为了确定出现此错误的时间，我们可以做的是使用异常语句，并告诉用户您输入了错误的日期，并且无法从该日期获取时间，因为该日期从未存在过，因此如何在该日期中存在时间。

## 蟒蛇 3

```
# import important module
import datetime
from datetime import datetime

# Create datetime string
datetime_str = "32JAN2022102356"
try:

    # call datetime.strptime to convert it into
    # datetime datatype
    datetime_obj = datetime.strptime(datetime_str,
                                     "%d%b%Y%H%M%S")

    # It will print the datetime object
    print("date time : {}".format(datetime_obj))
except:
    print("You have entered Incorrect Date, please enter a valid date")
```

**输出:**

> 您输入的日期不正确，请输入有效的日期