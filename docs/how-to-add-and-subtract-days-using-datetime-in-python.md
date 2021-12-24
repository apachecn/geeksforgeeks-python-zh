# 如何在 Python 中使用 DateTime 加减天数？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 中的日期时间加减天数/](https://www.geeksforgeeks.org/how-to-add-and-subtract-days-using-datetime-in-python/)

众所周知，日期和时间用在我们必须跟踪日期和时间的程序中，所以有必要有一个模块来操作日期和时间。在 python 中，**日期时间**模块处理日期和时间。**日期时间**模块内置 Python 标准库。

Datetime 模块由以下类组成:

<figure class="table">

|   | 

**名称**

 | 

**描述**

 |
| --- | --- | --- |
| 1. | **日期** | 它根据格鲁吉亚日历显示日期，属性是年、月和日。 |
| 2. | **时间** | 它显示时间，独立于任何特定的一天，属性有小时、分钟、秒、微秒和 tzinfo。 |
| 3. | **日期时间** | 它是日期和时间的集合，具有年、月、日、小时、分钟、秒、微秒和 tzinfo 属性。 |
| 4. | **时距增量** | 它被用来操纵日期。 |
| 5. | **tzinfo** | 它提供关于时区的信息。 |

</figure>

## **使用 Python 中的 DateTime 加减天数**

对于加减日期，我们使用了一个叫做 **timedelta()** 的函数，这个函数可以在 **datetime** 类下找到。它用于操作日期，我们可以对日期进行算术运算，如加或减。 **timedelta** 非常容易实现，也非常有用。

> **语法:** class datetime.timedelta(天数=10，秒=40，微秒=10，毫秒=60，分钟=10，小时=4，周=8)
> 
> **返回:**日期
> 
> **注意:**如果我们没有默认指定，则取整数为日。

**实施例 1。**添加天数

## 蟒蛇 3

```
# MANIPULATING DATETIME
from datetime import date, timedelta

today_date = date.today()

print("CURRENT DAY : ", today_date)

# as said earlier it takes argument as day by default
td = timedelta(5)
print("AFTER 5 DAYS DATE WILL BE : ", today_date + td)
```

**输出:**

```
CURRENT DAY :  2020-12-27
AFTER 5 DAYS DATE WILL BE :  2021-01-01
```

**例 2。**减去天数

## 蟒蛇 3

```
# MANIPULATING DATETIME
from datetime import date, timedelta

current_date = date.today()

print("CURRENT DAY : ",current_date)

print("OLD Date : ",current_date - timedelta(17))
```

**输出:**

```
CURRENT DAY :  2020-12-27
OLD Date :  2020-12-10
```

和上面的代码一样，我创建了一个名为 *current_date* 的变量，保存当前日期，然后打印该当前日期。

之后，我使用了 timedelta 函数，在参数中，我们传递了一个值，这个值表示要加或减多少天(这个值可以是任何整数)。

**同样，我们也可以用时间做同样的事情。**

**例 3:**

## 蟒蛇 3

```
# Manipulate DATETIME
from datetime import datetime, timedelta
current = datetime.now()
print("This is the current date and time :- ", current)

# FOR PRINTING TOMORROW'S DATE
tomorrow = timedelta(1)
print("Tomorrow's date and time :- ", current + tomorrow)

# FOR PRINTING YESTERDAY'S DATE
yesterday = timedelta(-1)
print("Yesterday's date and time :- ", current + yesterday)
```

**输出:**

```
This is the current date and time :-  2020-12-27 13:50:14.229336
Tomorrow's date and time :-  2020-12-28 13:50:14.229336
Yesterday's date and time :-  2020-12-26 13:50:14.229336
```

**例 4:**

## 蟒蛇 3

```
# MANIPULATING DATETIME
from datetime import datetime, timedelta

curr = datetime.now()
print("Current Date and time :- ", curr)

new_datetime = timedelta(days = 10, seconds = 40,
                         microseconds = 10,
                         milliseconds = 60,
                         minutes = 10, hours = 4,
                         weeks = 8)

print("New Date and time :- ", curr + new_datetime)
```

**输出:**

```
Current Date and time :-  2020-12-27 13:58:42.178211
New Date and time :-  2021-03-03 18:09:22.238221
```