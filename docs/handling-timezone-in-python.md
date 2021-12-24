# 在 Python 中处理时区

> 原文:[https://www.geeksforgeeks.org/handling-timezone-in-python/](https://www.geeksforgeeks.org/handling-timezone-in-python/)

有一些标准库我们可以用于时区，这里我们将使用 **pytz** 。这个库有一个时区类，用于处理来自世界协调时和时区的任意固定偏移量。

### 装置

**pytz** 是你必须安装的第三方软件包。要安装 pytz，请使用以下命令–

> pip 安装 pytz

### 入门指南

安装后，导入 pytz 包，现在让我们看看如何通过时区。Python 中获取日期和时间信息的基本语法是:

> datetime.datetime.now（）

上面的语法返回当前本地日期时间，没有任何时区信息。但是通过使用 pytz 包，我们可以在不同的时区处理这些日期时间信息—**now()**为我们提供了在时区中传递的选项，因此如果您将时区留空，它还将返回当前的本地日期时间。现在()的产量取决于机器。主机的本地时间和时区设置将决定输出。

因此，为了顺利使用时区，建议使用世界协调时作为您的基本时区。为了获得协调世界时，即世界协调时，我们只需将参数传递给 now()函数。要获取世界协调时时间，我们可以直接使用“pytz.utc”作为参数，将 now()函数设置为“now(pytz.utc)”。偏移量将在末尾显示为(+或–小时)。

下面的代码显示了机器的当地时间和带偏移的世界协调时时间。

**示例:**

## 蟒蛇 3

```py
import datetime
import pytz

dtObject_local = datetime.datetime.now()
dtObject_utc = datetime.datetime.now(pytz.utc)

print(dtObject_local)
print(dtObject_utc)
```

**输出:**

> 2021-05-28 12:19:56.962055
> 
> 2021-05-28 06:49:56.962055+00:00

如您所见，我们现在获得了本地机器的日期时间信息，以世界协调时表示，结束时的时区偏移量为+00:00。

如果我们想获得特定时区的日期时间信息，我们只需要在参数中添加时区–

**语法:**

> 。现在(pytz.timezone(' YOUR_TIMEZONE ')

参数 **pytz.timezone** 允许我们将时区信息指定为字符串。我们可以传入任何可用的时区，并将获得该时区的当前日期时间，它还将打印相对于世界协调时的偏移。即 UTC 时区(+00:00)和指定时区之间的差异。

**示例:**

## 蟒蛇 3

```py
import datetime
import pytz

dtObject_utc = datetime.datetime.now(pytz.utc)

dtObject_asia = datetime.datetime.now(pytz.timezone('Asia/Kolkata'))
dtObject_usc = datetime.datetime.now(pytz.timezone('US/Central'))
dtObject_turkey = datetime.datetime.now(pytz.timezone('Turkey'))
dtObject_eoslo = datetime.datetime.now(pytz.timezone('Europe/Oslo'))
dtObject_abelem = datetime.datetime.now(pytz.timezone('America/Belem'))

print(dtObject_utc)

print(dtObject_asia)
print(dtObject_usc)
print(dtObject_turkey)
print(dtObject_eoslo)
print(dtObject_abelem)
```

**输出:**

> 2021-05-28 23:12:56.559011+00:00
> 
> 2021-05-29 04:42:58.027452+05:30
> 
> 2021-05-28 18:12:58.072254-05:00
> 
> 2021-05-29 02:12:58.092257+03:00
> 
> 2021-05-29 01:12:58.107930+02:00
> 
> 2021-05-28 20:12:58.109932-03:00

这里我们根据不同的时区得到了不同的日期时间。偏移量还将显示(+/-)小时。我们还可以将任何时区转换为不同的时区。

### 在时区之间转换

**astimezone()** 方法用于操作，即将日期时间对象转换为新的指定日期时间对象。它使用 datetime 对象的一个实例，并返回新的时区信息。

**语法:**

> asti mezone(pytz . time zone(' NEW _ TIZONE ')

为了准确地得到我们所需要的，将遵循下面的语法。

**语法:**

> dtobj = datetimeobject _ instance . astmezone(pytz . time zone(' new _ time zone '))
> 
> 哪里，
> 
> *   dtObj:用新创建的时间日期存储返回的 datetime 对象
> *   datetimeObject_instance:当前可用的 datetime 对象(即对本地日期时间的引用)
> *   新时区:应该更改为的时区信息

**示例:**

## 蟒蛇 3

```py
import datetime
import pytz

# getting our local timezone
dtObject_local = datetime.datetime.now()

# converting local timezone to 'US/Central'
dtObject_usc = dtObject_local.astimezone(pytz.timezone('US/Central'))

# now converting 'US/Central' timezone to 'Pacific/Chuuk'
dtObject_pchuuk = dtObject_usc.astimezone(pytz.timezone('Pacific/Chuuk'))

print(dtObject_local)
print(dtObject_usc)
print(dtObject_pchuuk)
```

**输出:**

> 2021-05-29 04:46:26.288233
> 
> 2021-05-28 18:16:26.288233-05:00
> 
> 2021-05-29 09:16:26.288233+10:00

**pytz** 有一个很大的可用时区列表，您可以使用以下方法打印它们。

**示例:**

## 蟒蛇 3

```py
import pytz

for timeZone in pytz.all_timezones:
    print(timeZone)
```

**输出:**

> 非洲/阿比让
> 
> 非洲/阿克拉
> 
> 非洲/亚的斯亚贝巴
> 
> 非洲/阿尔及尔
> 
> 非洲/阿斯马拉
> 
> 。
> 
> 。
> 
> 。
> 
> 美国/萨摩亚
> 
> 协调世界时。亦称 COORDINATED UNIVERSAL TIME
> 
> 普遍的
> 
> w-苏
> 
> 湿的
> 
> 祖鲁语