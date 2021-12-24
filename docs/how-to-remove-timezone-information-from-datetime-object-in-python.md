# 如何在 Python 中删除 DateTime 对象的时区信息

> 原文:[https://www . geesforgeks . org/如何从 python 中的日期时间对象中删除时区信息/](https://www.geeksforgeeks.org/how-to-remove-timezone-information-from-datetime-object-in-python/)

时区被定义为一个地理区域或地区，标准时间贯穿其中。它基本上是指一个地区或国家的当地时间。大多数时区都偏离了世界时区标准协调世界时。

在本文中，我们将讨论如何从 DateTime 对象中移除时区信息。

## 使用的功能

*   **datetime.now(tz=None):** 返回当前本地日期和时间。
*   **datetime.replace():** 返回具有相同属性的日期时间，除了那些由指定的关键字参数赋予新值的属性。

要删除时间戳，在调用 replace()函数时，tzinfo 必须设置为 None。

首先，使用 ***datetime.now()创建一个具有当前时间的 DateTime 对象。*** 然后使用***time . utc .***修改日期时间对象以包含时区信息，然后使用 ***操作具有时区信息的日期时间对象。replace()*** 方法使用 ***tzinfo*** 参数删除时区信息。

**语法:**

> 替换(tzinfo =无)

**示例:**

## 计算机编程语言

```py
from datetime import datetime, timezone

# Get the datetime object using datetime
# module
dt_obj_w_tz = datetime.now()
print(dt_obj_w_tz)

# Add timezone information to the datetime
# object
dt_obj_w_tz = dt_obj_w_tz.replace(tzinfo=timezone.utc)
print(dt_obj_w_tz)

# Remove the timezone information from the datetime
# object
dt_obj_wo_tz = dt_obj_w_tz.replace(tzinfo=None)
print(dt_obj_wo_tz)
```

**输出:**

```py
2021-08-10 12:51:42.093388
2021-08-10 12:51:42.093388+00:00
2021-08-10 12:51:42.09338
```

但是，可以通过提供***【tz】***参数来创建带有时间戳的 datetime 对象。

**示例:**

## 计算机编程语言

```py
from datetime import datetime, timezone

# Get the datetime object with timezone
# information
dt_obj_w_tz = datetime.now(tz=timezone.utc)
print(dt_obj_w_tz)

# Remove the timezone information from the
# datetime object
dt_obj_wo_tz = dt_obj_w_tz.replace(tzinfo=None)
print(dt_obj_wo_tz)
```

**输出:**

```py
2021-08-10 07:21:57.838856+00:00
2021-08-10 07:21:57.838856
```