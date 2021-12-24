# 如何在 Python 中制作一个时区感知日期时间对象

> 原文:[https://www . geeksforgeeks . org/如何在 python 中创建时区感知日期时间对象/](https://www.geeksforgeeks.org/how-to-make-a-timezone-aware-datetime-object-in-python/)

在这个例子中，我们将看到如何在 Python 中创建一个时区敏感的 DateTime 对象。

时区感知对象是包含时区信息的 Python 日期时间或时间对象。一个有意识的物体代表了一个无法解释的特定时刻。

## 检查对象是否知道时区:

我们可以很容易地检查日期时间对象是否知道时区。为此，我们将使用 datetime 模块的 datetime.now()函数将当前日期和时间存储在一个新的变量中。

> **语法:** datetime.now(tz)
> 
> **参数:** tz:需要当前时间和日期的指定时区。(默认使用格林威治子午线时间。)

然后我们将检查存储在 tzinfo 基类中的对象的时区信息。tzinfo 是时区信息对象的抽象基类。

## 蟒蛇 3

```
# Importing the datetime module
import datetime

# Storing the current date and time in
# a new variable using the datetime.now()
# function of datetime module
current_date = datetime.datetime.now()

# Checking the timezone information of the
# object stored in tzinfo base class
if current_date.tzinfo == None or current_date.tzinfo.\
        utcoffset(current_date) == None:

    # If passes the above condition then
    # the object is unaware
    print("Unaware")
else:

    # Else printing "Aware"
    print("Aware")
```

**输出:**

```
Unaware
```

## 使用日期时间的时区感知对象

为此，我们将使用 datetime.now()将当前时间存储在一个新变量中。datetime 模块的 time()函数。然后我们将使用 replace()函数替换对象的 tzinfo 类中的时区值。之后，使用 isoformat()方法将日期值转换为 ISO 8601 格式。

> **语法:**等值格式(sep =‘t’，time pec =‘auto’)
> 
> **参数:**
> 
> *   **sep:** 是日期和时间之间的单字符分隔符。
> *   **时间点:**要包括的时间的附加分量的数量

**代码:**

## 蟒蛇 3

```
# Importing the datetime module
import datetime

# Storing the current date and time in
# a new variable using the datetime.now()
# function of datetime module
current_date = datetime.datetime.now()

# Replacing the value of the timezone in tzinfo class of
# the object using the replace() function
current_date = current_date.\
    replace(tzinfo=datetime.timezone.utc)

# Converting the date value into ISO 8601
# format using isoformat() method
current_date = current_date.isoformat()

# Printing the value of current_date
print(current_date)
```

**输出:**

```
2021-08-30T09:45:43.291212+00:00
```

现在，让我们使用本文第一部分中使用的方法来检查对象是否知道时区。

## 蟒蛇 3

```
# Importing the datetime module
import datetime

# Storing the current date and time in
# a new variable using the datetime.now()
# function of datetime module
current_date = datetime.datetime.now()

# Replacing the value of the timezone in tzinfo class of
# the object using the replace() function
current_date = current_date.replace(tzinfo=datetime.timezone.utc)

# Checking the timezone information of the
# object stored in tzinfo base class
if current_date.tzinfo == None or \
current_date.tzinfo.utcoffset(current_date) == None:

    # If passes the above condition then
    # the object is unaware
    print("Unaware")
else:

    # Else printing "Aware"
    print("Aware")

# Converting the date value into ISO 8601
# format using isoformat() method
current_date = current_date.isoformat()

# Printing the value of current_date
print(current_date)
```

**输出:**

```
Aware
2021-08-30T09:55:15.111556+00:00
```

## 使用 pytz 的时区感知对象

您也可以使用 pytz 模块来创建时区感知对象。

为此，我们将使用 datetime 模块的 datetime.now()函数将当前日期和时间存储在一个新变量中，然后使用 pytz 模块的 timezone 函数添加时区。

## 蟒蛇 3

```
# Importing the datetime module
import datetime
import pytz

# Storing the current date and time in
# a new variable using the datetime.now()
# function of datetime module and adding the timezone
# using timezone function of pytz module.
current_date = datetime.datetime.now(pytz.timezone('Africa/Abidjan'))

# Printing the value of current_date
print(current_date)
```

**输出:**

```
2021-08-30 04:35:37.036990+00:00
```

现在，让我们使用本文第一部分中使用的方法来检查对象是否知道时区。

## 蟒蛇 3

```
# Importing the datetime module
import datetime
import pytz

# Storing the current date and time in
# a new variable using the datetime.now()
# function of datetime module and adding the timezone
# using timezone function of pytz module.
current_date = datetime.datetime.now(pytz.timezone('Africa/Abidjan'))

# Checking the timezone information of the
# object stored in tzinfo base class
if current_date.tzinfo == None or current_date.\
tzinfo.utcoffset(current_date)== None:

    # If passes the above condition then
    # the object is unaware
    print("Unaware")
else:
    # Else printing "Aware"
    print("Aware")

# Printing the value of current_date
print(current_date)
```

**输出:**

```
Aware
2021-08-30 04:46:40.670455+00:00
```