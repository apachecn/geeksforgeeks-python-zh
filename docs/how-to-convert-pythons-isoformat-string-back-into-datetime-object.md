# 如何转换 Python 的。isoformat()字符串返回日期时间对象

> 原文:[https://www . geesforgeks . org/how-convert-python-isoformat-string-back-datetime-object/](https://www.geeksforgeeks.org/how-to-convert-pythons-isoformat-string-back-into-datetime-object/)

在本文中，我们将学习如何转换蟒蛇。isoFormat()字符串转换回日期时间对象。这里我们使用当前时间，为此，我们将当前时间存储在 current_time 变量中。

这个模块的 now()函数完美地完成了工作。

**示例:**获取当前时间

## 蟒蛇 3

```
from datetime import datetime

current_time = datetime.now()

print(current_time)
```

**输出:**

> 2021-07-22 15:17:19.735037

## 获取时间的字符串格式

在这一步中，我们将获得 iso 时间的字符串格式。为此，使用 isoformat()函数。

**示例:**获取时间的字符串格式

## 蟒蛇 3

```
from datetime import datetime

current_time = datetime.now().isoformat()
print(current_time)
```

**Output**

```
2021-07-26T11:36:17.090181

```

## 从 iso 格式获取日期时间对象

这里我们将从 iso 字符串中获取 DateTime 对象。为此，使用 fromisoformat()函数。

**示例**:从 iso 格式中获取 DateTime 对象

## 蟒蛇 3

```
from datetime import datetime

current_time = datetime.now().isoformat()

print(datetime.fromisoformat(current_time))
```

**输出:**

```
2021-07-26 17:06:51.149731
```