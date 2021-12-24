# Python 日期时间模块

> 原文:[https://www.geeksforgeeks.org/python-datetime-module/](https://www.geeksforgeeks.org/python-datetime-module/)

在 Python 中，日期和时间不是它们自己的数据类型，但是可以导入名为 **datetime** 的模块来处理日期和时间。 **Python Datetime 模块**内置于 Python 中，无需外接安装。

Python Datetime 模块提供了处理日期和时间的类。这些类提供了许多函数来处理日期、时间和时间间隔。日期和日期时间在 Python 中是一个对象，所以当您操作它们时，您实际上是在操作对象，而不是字符串或时间戳。

日期时间模块分为 6 个主要类别–

*   [**日期**](https://www.geeksforgeeks.org/python-datetime-date-class/)–一个理想化的天真日期，假设当前公历一直有效，并且将一直有效。它的属性是年、月、日。
*   [**时间**](https://www.geeksforgeeks.org/python-datetime-time-class/)–一个理想化的时间，独立于任何特定的一天，假设每天正好有 24*60*60 秒。它的属性是小时、分钟、秒、微秒和 tzinfo。
*   [](https://www.geeksforgeeks.org/python-datetime-datetime-class/)**–它是日期和时间以及年、月、日、时、分、秒、微秒和 tzinfo 属性的组合。**
*   **[**时间增量**](https://www.geeksforgeeks.org/python-datetime-timedelta-class/)–表示两个日期、时间或日期时间实例之间差异的持续时间，分辨率为微秒。**
*   ****tzinfo**–提供时区信息对象。**
*   ****时区**–将 tzinfo 抽象基类实现为与世界协调时的固定偏移量的类(3.2 版本中新增)。**

## **日期类别**

**[日期类](https://www.geeksforgeeks.org/python-datetime-date-class/)用于在 Python 中实例化日期对象。当这个类的对象被实例化时，它以 YYYY-MM-DD 的格式表示一个日期。这个类的构造函数需要三个强制参数年、月和日。**

****构造函数语法:****

```
class datetime.date(year, month, day)
```

**参数必须在以下范围内–**

*   **MINYEAR <= year <= MAXYEAR**
*   **1 <=月< = 12**
*   **1 <=天< =给定月份和年份中的天数**

****注意**–如果参数不是整数，它将引发类型错误，如果超出范围，将引发值错误。**

### **示例 Python 中表示日期的日期对象**

## **蟒蛇 3**

```
# Python program to
# demonstrate date class

# import the date class
from datetime import date

# initializing constructor
# and passing arguments in the
# format year, month, date
my_date = date(1996, 12, 11)

print("Date passed as argument is", my_date)

# Uncommenting my_date = date(1996, 12, 39)
# will raise an ValueError as it is
# outside range

# uncommenting my_date = date('1996', 12, 11)
# will raise a TypeError as a string is
# passed instead of integer
```

****输出:****

```
Date passed as argument is 1996-12-11
```

```
Traceback (most recent call last):
  File "/home/ccabfb570d9bd1dcd11dc4fe55fd6ba2.py", line 14, in 
    my_date = date(1996, 12, 39)
ValueError: day is out of range for month

Traceback (most recent call last):
  File "/home/53b974e10651f1853eee3c004b48c481.py", line 18, in 
    my_date = date('1996', 12, 11)
TypeError: an integer is required (got type str) 
```

### **示例 2:获取当前日期**

**使用 date 类的 today()函数返回当前的本地日期。today()函数带有几个属性(年、月和日)。这些可以单独打印。**

## **蟒蛇 3**

```
# Python program to
# print current date

from datetime import date

# calling the today
# function of date class
today = date.today()

print("Today's date is", today)
```

****Output**

```
Today's date is 2021-08-19
```** 

### **示例 3:获取今天的年、月和日期**

**我们可以使用 date 类的年、月和日期属性从 date 对象中获取年、月和日期属性。**

## **蟒蛇 3**

```
from datetime import date

# date object of today's date
today = date.today()

print("Current year:", today.year)
print("Current month:", today.month)
print("Current day:", today.day)
```

****Output**

```
Current year: 2021
Current month: 8
Current day: 19
```** 

### **示例 4:从时间戳获取日期**

**我们可以使用 fromtimestamp()方法从时间戳 y =创建日期对象。时间戳是从世界协调时 1970 年 1 月 1 日到特定日期的秒数。**

## **蟒蛇 3**

```
from datetime import datetime

# Getting Datetime from timestamp
date_time = datetime.fromtimestamp(1887639468)
print("Datetime from timestamp:", date_time)
```

****Output**

```
Datetime from timestamp: 2029-10-25 16:17:48
```** 

### **示例 5:将日期转换为字符串**

**我们可以使用两个函数 isoformat()和 strftime()将 date 对象转换为字符串表示形式。**

## **蟒蛇 3**

```
from datetime import date

# calling the today
# function of date class
today = date.today()

# Converting the date to the string
Str = date.isoformat(today)
print("String Representation", Str)
print(type(Str))
```

****Output**

```
String Representation 2021-08-19
<class 'str'>
```** 

### **日期类方法列表**

<figure class="table">

| 函数名 | 描述 |
| --- | --- |
| ctime() | 返回表示日期的字符串 |
| fromisocialendar _) | 返回与国际标准化组织日历对应的日期 |
| fromisoformat() | 从日期的字符串表示形式返回日期对象 |
| from 序数() | 从公历序数返回日期对象，其中第 1 年的 1 月 1 日具有序数 1 |
| [来自时间戳（）](https://www.geeksforgeeks.org/fromtimestamp-function-of-datetime-date-class-in-python/) | 从 POSIX 时间戳返回一个日期对象 |
| isocialendar _) | 返回一个元组年、周和工作日 |
| 异格式() | 返回日期的字符串表示形式 |
| 等星期日（） | 以整数形式返回一周中的某一天，其中周一为 1，周日为 7 |
| 替换() | 使用给定参数更改日期对象的值 |
| strftime（） | 以给定格式返回日期的字符串表示形式 |
| 时间图() | 返回 time.struct_time 类型的对象 |
| 今日() | 返回当前本地日期 |
| toordinal() | 返回日期的公历序数，其中第 1 年的 1 月 1 日具有序数 1 |
| 工作日() | 以整数形式返回一周中的某一天，其中周一为 0，周日为 6 |

</figure>

## **时间类**

**[时间类](https://www.geeksforgeeks.org/python-datetime-time-class/)创建代表本地时间的时间对象，与任何一天无关。**

****构造函数语法:****

> **class datetime.time(小时=0，分钟=0，秒=0，微秒=0，tzinfo=None，* fold = 0)**

**所有参数都是可选的。tzinfo 可以是无，否则所有属性必须是以下范围内的整数–**

*   **0 <=小时< 24**
*   **0 <=分钟< 60**
*   **0 <=秒< 60**
*   **0 <=微秒< 1000000**
*   **折叠[0，1]**

### **示例 Python 中表示时间的时间对象**

## **蟒蛇 3**

```
# Python program to
# demonstrate time class

from datetime import time

# calling the constructor
my_time = time(13, 24, 56)

print("Entered time", my_time)

# calling constructor with 1
# argument
my_time = time(minute=12)
print("\nTime with one argument", my_time)

# Calling constructor with
# 0 argument
my_time = time()
print("\nTime without argument", my_time)

# Uncommenting time(hour = 26)
# will rase an ValueError as
# it is out of range

# uncommenting time(hour ='23')
# will raise TypeError as
# string is passed instead of int
```

****输出:****

```
Entered time 13:24:56

Time with one argument 00:12:00

Time without argument 00:00:00
```

```
Traceback (most recent call last):
  File "/home/95ff83138a1b3e67731e57ec6dddef25.py", line 21, in 
    print(time(hour=26))
ValueError: hour must be in 0..23

Traceback (most recent call last):
  File "/home/fcee9ba5615b0b74fc3ba39ec9a789fd.py", line 21, in 
    print(time(hour='23'))
TypeError: an integer is required (got type str)
```

### **示例 2:获取小时、分钟、秒和微秒**

**创建时间对象后，也可以单独打印其属性。**

## **蟒蛇 3**

```
from datetime import time

Time = time(11, 34, 56)

print("hour =", Time.hour)
print("minute =", Time.minute)
print("second =", Time.second)
print("microsecond =", Time.microsecond)
```

****输出:****

```
hour = 11
minute = 34
second = 56
microsecond = 0
```

### **示例 3:将时间对象转换为字符串**

**我们可以使用 isoformat()方法将时间对象转换为字符串。**

## **蟒蛇 3**

```
from datetime import time

# Creating Time object
Time = time(12,24,36,1212)

# Converting Time object to string
Str = Time.isoformat()
print("String Representation:", Str)
print(type(Str))
```

****Output**

```
String Representation: 12:24:36.001212
<class 'str'>
```** 

### **时间类方法列表**

<figure class="table">

| 函数名 | 描述 |
| --- | --- |
| dst() | 返回 tzinfo . dst()。tzinfo 不是无 |
| fromisoformat() | 从时间的字符串表示形式返回时间对象 |
| 异格式() | 从 time 对象返回时间的字符串表示形式 |
| 替换() | 使用给定参数更改时间对象的值 |
| strftime（） | 以给定格式返回时间的字符串表示形式 |
| tzname() | 返回 tzinfo . tzname()。tzinfo 不是无 |
| utcoffset() | 返回 tzinfo.utcffsets()。如果 tzinfo 不是“无” |

</figure>

## **日期时间类**

**[日期时间类](https://www.geeksforgeeks.org/python-datetime-datetime-class/)包含日期和时间信息。像日期对象一样，日期时间假定当前公历在两个方向上扩展；像时间对象一样，datetime 假设每天正好有 3600*24 秒。**

****构造函数语法:****

> **class datetime.datetime(年、月、日、小时=0，分钟=0，秒=0，微秒=0，tzinfo=None，* fold = 0)**

**年、月和日参数是必需的。tzinfo 可以是无，其余所有属性必须是以下范围内的整数–**

*   **MINYEAR <= year <= MAXYEAR**
*   **1 <=月< = 12**
*   **1 <=天< =给定月份和年份中的天数**
*   **0 <=小时< 24**
*   **0 <=分钟< 60**
*   **0 <=秒< 60**
*   **0 <=微秒< 1000000**
*   **折叠[0，1]**

****注意**–传递整数以外的参数将引发类型错误，传递超出范围的参数将引发值错误。**

### **示例 1:用 Python 表示日期时间的日期时间对象**

## **蟒蛇 3**

```
# Python program to
# demonstrate datetime object

from datetime import datetime

# Initializing constructor
a = datetime(1999, 12, 12)
print(a)

# Initializing constructor
# with time parameters as well
a = datetime(1999, 12, 12, 12, 12, 12, 342380)
print(a)
```

****输出:****

```
1999-12-12 00:00:00
1999-12-12 12:12:12.342380
```

### **示例 2:获取年、月、小时、分钟和时间戳**

**创建日期时间对象后，也可以单独打印其属性。**

## **蟒蛇 3**

```
from datetime import datetime

a = datetime(1999, 12, 12, 12, 12, 12)

print("year =", a.year)
print("month =", a.month)
print("hour =", a.hour)
print("minute =", a.minute)
print("timestamp =", a.timestamp())
```

****输出:****

```
year = 1999
month = 12
hour = 12
minute = 12
timestamp = 945000732.0
```

### **示例 3:当前日期和时间**

**您可以使用 Datetime.now()函数打印当前日期和时间。now()函数返回当前的本地日期和时间。**

## **蟒蛇 3**

```
from datetime import datetime

# Calling now() function
today = datetime.now()

print("Current date and time is", today)
```

****输出:****

```
Current date and time is 2019-10-25 11:12:11.289834
```

### **示例 4:将 Python 日期时间转换为字符串**

**我们可以在 Python 中使用[Datetime . str time](https://www.geeksforgeeks.org/python-strftime-function/)和 datetime.isoformat 方法将 Datetime 转换为字符串。**

## **蟒蛇 3**

```
from datetime import datetime as dt

# Getting current date and time
now = dt.now()

string = dt.isoformat(now)
print(string)
print(type(string))
```

****Output**

```
2021-08-19T18:13:25.346259
<class 'str'>
```** 

### **日期时间类方法列表**

<figure class="table">

| 函数名 | 描述 |
| --- | --- |
| astimezone() | 返回包含时区信息的日期时间对象。 |
| 结合 | 组合日期和时间对象，并返回一个日期时间对象 |
| ctime() | 返回日期和时间的字符串表示形式 |
| 日期() | 返回日期类对象 |
| fromisoformat() | 从日期和时间的字符串表示形式返回 datetime 对象 |
| from 序数() | 从公历序数返回日期对象，其中第 1 年的 1 月 1 日具有序数 1。小时、分钟、秒和微秒是 0 |
| 来自时间戳（） | 从 POSIX 时间戳返回日期和时间 |
| isocialendar _) | 返回一个元组年、周和工作日 |
| 异格式() | 返回日期和时间的字符串表示 |
| 等星期日（） | 以整数形式返回一周中的某一天，其中周一为 1，周日为 7 |
| 现在() | 使用 tz 参数返回当前本地日期和时间 |
| 替换() | 更改日期时间对象的特定属性 |
| strftime（） | 以给定格式返回日期时间对象的字符串表示形式 |
| strptime（） | 返回与日期字符串对应的日期时间对象 |
| 时间() | 返回时间类对象 |
| 时间图() | 返回 time.struct_time 类型的对象 |
| 时间表() | 返回时间类对象 |
| 今日() | 返回本地日期时间，tzinfo 为无 |
| toordinal() | 返回日期的公历序数，其中第 1 年的 1 月 1 日具有序数 1 |
| tzname() | 返回时区的名称 |
| utcfromtimestamp() | 从 POSIX 时间戳返回世界协调时 |
| utcoffset() | 返回世界协调时偏移 |
| utcnow() | 返回当前世界协调时日期和时间 |
| 工作日() | 以整数形式返回一周中的某一天，其中周一为 0，周日为 6 |

</figure>

## **时间增量类**

**Python [timedelta](https://www.geeksforgeeks.org/python-datetime-timedelta-class/) 类用于计算日期差异，也可以用于 Python 中的日期操作。这是执行日期操作最简单的方法之一。**

****构造函数语法:****

> **类 datetime.timedelta(天=0，秒=0，微秒=0，毫秒=0，分钟=0，小时=0，周=0)
> 返回:Date**

### **示例 1:向日期时间对象添加日期**

## **蟒蛇 3**

```
# Timedelta function demonstration

from datetime import datetime, timedelta

# Using current time
ini_time_for_now = datetime.now()

# printing initial_date
print("initial_date", str(ini_time_for_now))

# Calculating future dates
# for two years
future_date_after_2yrs = ini_time_for_now + timedelta(days=730)

future_date_after_2days = ini_time_for_now + timedelta(days=2)

# printing calculated future_dates
print('future_date_after_2yrs:', str(future_date_after_2yrs))
print('future_date_after_2days:', str(future_date_after_2days))
```

****输出:****

```
initial_date 2019-10-25 12:01:01.227848
future_date_after_2yrs: 2021-10-24 12:01:01.227848
future_date_after_2days: 2019-10-27 12:01:01.227848
```

### **示例 2:两个日期和时间之间的差异**

**使用此类还可以找到日期和时间差异。**

## **蟒蛇 3**

```
# Timedelta function demonstration
from datetime import datetime, timedelta

# Using current time
ini_time_for_now = datetime.now()

# printing initial_date
print("initial_date", str(ini_time_for_now))

# Some another datetime
new_final_time = ini_time_for_now + \
    timedelta(days=2)

# printing new final_date
print("new_final_time", str(new_final_time))

# printing calculated past_dates
print('Time difference:', str(new_final_time -
                              ini_time_for_now))
```

****输出:****

```
initial_date 2019-10-25 12:02:32.799814
new_final_time 2019-10-27 12:02:32.799814
Time difference: 2 days, 0:00:00
```

### **时间增量类支持的操作**

<figure class="table">

| 操作员 | 描述 |
| --- | --- |
| 加法(+) | 添加并返回两个时间增量对象 |
| 减法(-) | 减去并返回两个时间增量对象 |
| 乘法(*) | 将时间增量对象乘以浮点或整数 |
| 分部(/) | 用浮点数或整数除 timedelta 对象 |
| 楼层划分(//) | 用 float 或 int 除 timedelta 对象，并返回输出的整数值 |
| 模(%) | 将两个时间增量对象相除，并返回余数 |
| +(小时增量) | 返回相同的时间增量对象 |
| -每小时一次 | 返回-1 *时间增量的结果 |
| abs(时间差) | 如果时间增量天数> 1=0，则返回+(时间增量)，否则返回-(时间增量) |
| str(时间差) | 返回一个格式为(+/-)天的字符串，HH:MM:SS。UUUUUU |
| rep(小时增量) | 返回构造函数调用形式的字符串表示形式 |

</figure>

## **格式日期时间**

**格式化 Datetime 可能是非常必要的，因为日期表示可能因地而异。像在一些国家，它可以是 yyyy-mm-dd，在其他国家，它可以是 DD-mm-yyy。要格式化 Python Datetime，可以使用 str time 和 str time 函数。**

## **Python Datetime strftime**

**方法将给定的日期、时间或日期时间对象转换为给定格式的字符串表示形式。**

### **示例:Python Datetime 格式**

## **蟒蛇 3**

```
# Python program to demonstrate
# strftime() function

from datetime import datetime as dt

# Getting current date and time
now = dt.now()
print("Without formatting", now)

# Example 1
s = now.strftime("%A %m %-Y")
print('\nExample 1:', s)

# Example 2
s = now.strftime("%a %-m %y")
print('\nExample 2:', s)

# Example 3
s = now.strftime("%-I %p %S")
print('\nExample 3:', s)

# Example 4
s = now.strftime("%H:%M:%S")
print('\nExample 4:', s)
```

****Output**

```
Without formatting 2021-08-19 18:16:25.881661

Example 1: Thursday 08 2021

Example 2: Thu 8 21

Example 3: 6 PM 25

Example 4: 18:16:25
```** 

****注:**详见[str time()方法](https://www.geeksforgeeks.org/python-strftime-function/)。**

## **Python DateTime strptime**

**strptime()从给定的字符串创建一个 datetime 对象。**

### **示例：日期时间 strptime**

## **蟒蛇 3**

```
# import datetime module from datetime
from datetime import datetime

# consider the time stamps from a list  in string
# format DD/MM/YY H:M:S.micros
time_data = ["25/05/99 02:35:8.023", "26/05/99 12:45:0.003",
             "27/05/99 07:35:5.523", "28/05/99 05:15:55.523"]

# format the string in the given format : day/month/year 
# hours/minutes/seconds-micro seconds
format_data = "%d/%m/%y %H:%M:%S.%f"

# Using strptime with datetime we will format string
# into datetime
for i in time_data:
    print(datetime.strptime(i, format_data))
```

****Output**

```
1999-05-25 02:35:08.023000
1999-05-26 12:45:00.003000
1999-05-27 07:35:05.523000
1999-05-28 05:15:55.523000
```** 

## **处理 Python 日期时间时区**

**日期时间中的时区可用于希望根据特定区域的时区显示时间的情况。这可以使用 Python 的 [pytz 模块](https://www.geeksforgeeks.org/python-pytz/)来完成。该模块提供日期时间转换功能，并帮助用户服务于国际客户群。**

## **蟒蛇 3**

```
from datetime import datetime
from pytz import timezone

format = "%Y-%m-%d %H:%M:%S %Z%z"

# Current time in UTC
now_utc = datetime.now(timezone('UTC'))
print(now_utc.strftime(format))

timezones = ['Asia/Kolkata', 'Europe/Kiev', 'America/New_York']

for tzone in timezones:

    # Convert to Asia/Kolkata time zone
    now_asia = now_utc.astimezone(timezone(tzone))
    print(now_asia.strftime(format))
```

****Output**

```
2021-08-19 18:27:28 UTC+0000
2021-08-19 23:57:28 IST+0530
2021-08-19 21:27:28 EEST+0300
2021-08-19 14:27:28 EDT-0400
```**