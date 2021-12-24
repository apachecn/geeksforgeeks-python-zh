# Python datetime.timetz()方法示例

> 原文:[https://www . geesforgeks . org/python-datetime-timetz-method-with-example/](https://www.geeksforgeeks.org/python-datetime-timetz-method-with-example/)

函数的作用是:操作日期时间模块的日期时间类的对象。这个函数使用通过引用给它的实例方法，并转换它们，返回一个具有相同小时、分钟、秒、微秒以及 fold 和 tzinfo 属性的时间对象。

> **语法:** timetz()
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回一个时间对象，该时间对象具有相同的指定小时、分钟、秒、微秒、折叠和 tzinfo。

**例 1:** Python 程序展示 timetz()函数的应用。

## 蟒蛇 3

```py
# Python3 code for getting
# a time object with the same
# specified hour, minute, second,
# microsecond, fold and tzinfo.

# Importing datetime module
import datetime

# Creating a datetime instance
A = datetime.datetime(2021, 8, 3, 10, 11, 12, 13)

# Calling the timetz() function over
# the above datetime instance
B = A.timetz()

# Printing the original date time object
print("Original date time object:", A)

# Printing the new time object
print("New time object:", B)
```

**Output**

```py
Original date time object: 2021-08-03 10:11:12.000013
New time object: 10:11:12.000013

```

**例 2:** Python 程序展示 timetz()函数的应用。

## 蟒蛇 3

```py
# Python3 code for getting
# a time object with the same
# specified hour, minute, second,
# microsecond, fold and tzinfo.

# Importing datetime module
import datetime

# Creating a current datetime instance
A = datetime.datetime.now()

# Calling the timetz() function over
# the above current datetime instance
B = A.timetz()

# Printing the original current date time object
print("Original current date time object:", A)

# Printing the new current time object
print("New current time object:", B)
```

**Output**

```py
Original current date time object: 2021-08-05 07:41:24.147260
New current time object: 07:41:24.147260

```

**示例 3:** Python 程序展示 timetz()函数的应用。

## 蟒蛇 3

```py
# Python3 code for getting
# a time object with the same
# specified hour, minute, second,
# microsecond, fold and tzinfo.

# Importing datetime module
import datetime

# Creating datetime instances
A = datetime.timedelta(hours=12, minutes=12)
obj = datetime.timezone(A, name="IST")
B = datetime.datetime(2012, 1, 2, 3, 10, 15, 20, obj)

# Calling the timetz() function over the above
# specified datetime
C = B.timetz()

# Printing the Original datetime object
print("Original datetime object:", B)

# Printing the time object with tzinfo attributes
print("Time object with tzinfo attributes:", C)

# Printing the time object without tzinfo attributes
print("Time object without tzinfo attributes:", B.time())
```

**Output**

```py
Original datetime object: 2012-01-02 03:10:15.000020+12:12
Time object with tzinfo attributes: 03:10:15.000020+12:12
Time object without tzinfo attributes: 03:10:15.000020

```