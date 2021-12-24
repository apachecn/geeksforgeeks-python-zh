# Python DateTime – DateTime Class

> 原文:[https://www . geesforgeks . org/python-datetime-datetime-class/](https://www.geeksforgeeks.org/python-datetime-datetime-class/)

日期时间模块的日期时间类，顾名思义，既包含日期信息，也包含时间信息。像日期对象一样，DateTime 假设当前公历在两个方向上扩展；像时间对象一样，DateTime 假设每天正好有 3600*24 秒。但是与日期类不同，日期类的对象是潜在的感知对象，即它也包含关于时区的信息。

**语法:**

> class datetime.datetime(年、月、日、小时=0，分钟=0，秒=0，微秒=0，tzinfo=None，* fold = 0)

年、月和日参数是必需的。tzinfo 可以是无，其余所有属性必须是以下范围内的整数–

*   MINYEAR(1) <= year <= MAXYEAR(9999)
*   1 <=月< = 12
*   1 <=天< =给定月份和年份中的天数
*   0 <=小时< 24
*   0 <=分钟< 60
*   0 <=秒< 60
*   0 <=微秒< 1000000
*   折叠[0，1]

**注意:**传递整数以外的参数将引发类型错误，传递范围以外的参数将引发值错误。

**示例:**创建日期时间类的实例

## 蟒蛇 3

```
# Python program to
# demonstrate datetime object

from datetime import datetime

# Initializing constructor
a = datetime(2022, 10, 22)
print(a)

# Initializing constructor
# with time parameters as well
a = datetime(2022, 10, 22, 6, 2, 32, 5456)
print(a)
```

**Output**

```
2022-10-22 00:00:00
2022-10-22 06:02:32.005456
```

## 类别属性

让我们看看这个类提供的属性–

<figure class="table">

| 属性名 | 描述 |
| --- | --- |
| 部 | 可表示的最小日期时间 |
| 最大 | 可表示的最大日期时间 |
| 解决 | 日期时间对象之间的最小可能差异 |
| 年 | 年的范围必须在最小年和最大年之间 |
| 月 | 月份范围必须介于 1 和 12 之间 |
| 天 | 日期范围必须介于 1 和给定年份的给定月份中的天数之间 |
| 小时 | 小时范围必须介于 0 和 24 之间(不包括 24) |
| 分钟 | 分钟范围必须介于 0 和 60 之间(不包括 60) |
| 第二 | 秒的范围必须介于 0 和 60 之间(不包括 60) |
| 微秒 | 微秒范围必须介于 0 和 1000000 之间(不包括 1000000) |
| 齐 info | 包含时区信息的对象 |
| 折叠 | 表示折叠是否发生在 |

</figure>

**示例 1:** 获取可表示的最小和最大日期时间对象

## 蟒蛇 3

```
from datetime import datetime

# Getting min datetime
mindatetime = datetime.min
print("Min DateTime supported", mindatetime)

# Getting max datetime
maxdatetime = datetime.max
print("Max DateTime supported", maxdatetime)
```

**Output**

```
Min DateTime supported 0001-01-01 00:00:00
Max DateTime supported 9999-12-31 23:59:59.999999
```

**示例 2:** 访问日期和时间对象的属性

## 蟒蛇 3

```
from datetime import datetime

# Getting Today's Datetime
today = datetime.now()

# Accessing Attributes
print("Day: ", today.day)
print("Month: ", today.month)
print("Year: ", today.year)
print("Hour: ", today.hour)
print("Minute: ", today.minute)
print("Second: ", today.second)
```

**Output**

```
Day:  26
Month:  7
Year:  2021
Hour:  16
Minute:  24
Second:  7
```

## 类函数

DateTime 类提供了各种函数来处理 DateTime 对象，比如我们可以将 DateTime 对象转换为字符串，将字符串转换为 DateTime 对象，我们还可以获取特定月份的特定日期的工作日，我们还可以为特定 DateTime 对象设置时区等。

### 日期时间类方法列表

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

**示例 1:** 获取今天的日期

## 蟒蛇 3

```
from datetime import datetime

# Getting Today's Datetime
today = datetime.now()
print("Today's date using now() method:", today)

today = datetime.today()
print("Today's date using today() method:", today)
```

**输出**

> 使用 now()方法的今日日期:2021-07-26 22:23:22.725573
> 
> 使用 Today()方法的今日日期:2021-07-26 22:23:22.725764

**示例 2:** 从时间戳和序号获取日期时间

## 蟒蛇 3

```
from datetime import datetime

# Getting Datetime from timestamp
date_time = datetime.fromtimestamp(1887639468)
print("Datetime from timestamp:", date_time)

# Getting Datetime from ordinal
date_time = datetime.fromordinal(737994)
print("Datetime from ordinal:", date_time)
```

**Output**

```
Datetime from timestamp: 2029-10-25 16:17:48
Datetime from ordinal: 2021-07-23 00:00:00
```

**注:**关于 Python Datetime 的更多信息，请参考 [Python Datetime 教程](https://www.geeksforgeeks.org/python-datetime-module/)