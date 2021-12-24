# 在 Python 中添加日期和时间

> 原文:[https://www . geeksforgeeks . org/python 中添加日期和时间/](https://www.geeksforgeeks.org/adding-dates-and-times-in-python/)

**先决条件:**[Python–datetime . tzinfo()](https://www.geeksforgeeks.org/python-datetime-tzinfo/)

Python 支持日期时间模块来执行日期和时间操作。Datetime 模块允许用户执行各种与日期和时间相关的算术运算，提取各种时间框架并格式化不同格式的输出。这些类型的对象是不可变的。可以使用以下命令将模块导入 Python 工作区:

```
import datetime
```

datetime 对象还支持附加的时区属性，这是可选的。该属性可以分配给 tzinfo 类的子类实例。tzinfo 对象类可以满足以下要求，即捕获与世界协调时时间的固定偏移相关的信息，即世界协调时本身或北美东部时间和东部时间时区、相应时区的名称，以及夏令时当前是否有效。tzinfo 是一个抽象基类。tzinfo 的任意具体子类可能需要实现自己的方法。时区偏移量是指时区距离协调世界时(UTC)的小时数。

## **使用 tzinfo** 确定日期时间对象的类型

有两种对象，天真的和感知的，如果对象不包含任何时区信息，那么日期时间对象是天真的，否则感知的。对于简单对象，tzinfo 返回 None。

## 蟒蛇 3

```
# importing required module
import datetime

# create object
datetime_obj = datetime.datetime.now()

print(datetime_obj.tzinfo)
```

**输出:**

```
None
```

在这种情况下，我们需要使用感知日期时间对象，可以显式指定时区。pytz 库可用于本地化创建的 datetime 对象，该对象提供有关创建的时区的信息。无法比较天真日期时间和感知日期时间对象，否则将引发错误。

## 蟒蛇 3

```
# importing the required modules
import datetime
import pytz

# instantiate datetime object
obj = datetime.datetime.now()

# specifying the timezone using pytz library
tzone = pytz.timezone("America/Los_Angeles")

# localizing the datetime object
datetime_obj = tzone.localize(obj)

# extracting time zone info of the object
print(datetime_obj.tzinfo)
```

**输出:**

```
America/Los_Angeles
```

## **替换日期时间对象的时区**

使用 datetime.now()对象实例化了一个简单的时区对象。可以使用 pytz.timezone()模块显式指定新时区。然后进一步使用指定的时区。在 datetime 对象上调用 replace 方法，并将 tzinfo 参数设置为被替换的时区值。然后，使用 astimezone()方法在幼稚时区对象上提取该值，并将更改的时区作为其参数。

## 蟒蛇 3

```
# importing required modules
from datetime import datetime
import pytz

# creating a datetime object
curr_datetime = datetime.now()
print("Current timezone")
print(curr_datetime)

# creating timezone using pytz package
changed_timezone = pytz.timezone('US/Pacific')

# replacing timezone using the specified timezone value
curr_datetime = curr_datetime.replace(tzinfo=changed_timezone)
curr_datetime = curr_datetime.astimezone(changed_timezone)
print("Replaced timezone")
print(curr_datetime)
```

**输出:**

```
Current timezone
2021-02-12 20:20:50.668454
Replaced timezone
2021-02-12 20:20:50.668454-07:53
```