# 在 Python 中格式化日期

> 原文:[https://www.geeksforgeeks.org/formatting-dates-in-python/](https://www.geeksforgeeks.org/formatting-dates-in-python/)

在世界的不同地区，使用不同类型的日期格式，因此，编程语言通常为开发人员提供多种日期格式来处理。在 Python 中，它是通过使用名为`[datetime](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)`的自由来处理的。它由可用于处理数据和时间值的类和方法组成。

要使用它，首先通过以下方式导入日期时间库:

```
import datetime
```

我们可以在日期时间中包含以下组件:

*   **The time class**

    时间值可以使用时间类来表示。时间类的属性包括小时、分钟、秒和微秒。时间的一个例子如下:

    **语法:**

    ```
    time(hour, minute, second, microsecond)

    ```

    **示例:**

    ```
    import datetime

    tm = datetime.time(2, 25, 50, 13)
    print(tm)
    ```

    **输出**

    ```
    02:25:50.000013

    ```

    时间属性有范围，即秒的范围在 0 到 59 之间，纳秒的范围在 0 到 999999 之间。如果超出范围，编译器显示一个`ValueError`。

    时间类的实例由三个实例属性组成，即小时、分钟、秒和微秒。这些用于获取具体的时间信息。

    **示例:**

    ```
    import datetime

    tm = datetime.time(1, 50, 20, 133257)

    print('Time tm is ',
          tm.hour, ' hours ',
          tm.minute, ' minutes ',
          tm.second, ' seconds and ',
          tm.microsecond, ' microseconds' )
    ```

    **输出**

    > 时间 tm 是 1 小时 50 分 20 秒 133257 微秒

*   **The date class**

    日历日期的值可以通过日期类来表示。日期实例由年、月和日的属性组成。

    **语法:**

    ```
    date(yyyy, mm, dd)

    ```

    **示例:**

    ```
    import datetime

    date = datetime.date(2018, 5, 12)
    print('Date date is ', date.day,
          ' day of ', date.month,
          ' of the year ', date.year)
    ```

    **输出**

    ```
    Date date is  12  day of  5  of the year  2018

    ```

    为了获得今天的日期名称，使用了名为 **today()** 的方法，并且为了获得一个对象中的所有信息，使用了`ctime()`方法。

    **示例:**

    ```
    import datetime

    tday = datetime.date.today()
    daytoday = tday.ctime()

    print("The date today is ", tday)
    print("The date info. is ", daytoday)
    ```

    **输出**

    ```
    The date today is  2020-01-30
    The date info. is  Thu Jan 30 00:00:00 2020

    ```

#### 将日期转换为字符串

日期和时间不同于字符串，因此很多时候将日期时间转换为字符串是很重要的。为此我们使用`strftime()`方法。

**语法:**

```
time.strftime(format, t)

```

**参数:**

*   **格式–**这是字符串类型。即指令可以嵌入格式字符串中。
*   **t–**要格式化的时间。

**示例:**

```
import datetime

x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)

print(x.strftime("%b %d %Y %H:%M:%S"))
```

**输出**

```
May 12 2018 02:25:50
```

同样的例子也可以通过设置`print()`方法写成不同的地方。

```
import datetime

x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)

print(x.strftime("%H:%M:%S %b %d %Y"))
```

**输出**

```
02:25:50 May 12 2018 
```

%H、%M 和%S 分别显示小时、分钟和秒。%b、%d 和%Y 分别显示月、日和年的 3 个字符。

除了上述示例之外，常用字符代码列表及其功能还有:

*   **%a:** Displays three characters of the weekday, e.g. Wed.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("%a"))
    ```

    **输出**

    ```
    Sat

    ```

*   **%A:** Displays name of the weekday, e.g. Wednesday.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("%A"))
    ```

    **输出**

    ```
    Saturday

    ```

*   **%B:** Displays the month, e.g. May.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("%B"))
    ```

    **输出**

    ```
    May

    ```

*   **%w:** Displays the weekday as a number, from 0 to 6, with Sunday being 0.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("%w"))
    ```

    **输出**

    ```
    6

    ```

*   **%m:** Displays month as a number, from 01 to 12.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("%m"))
    ```

    **输出**

    ```
    5

    ```

*   **%p:** Define AM/PM for time.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("%p"))
    ```

    **输出**

    ```
    PM

    ```

*   **%y:** Displays year in two-digit format, i.e “20” in place of “2020”.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("% y"))
    ```

    **输出**

    ```
    18

    ```

*   **%f:** Displays microsecond from 000000 to 999999.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("% f"))
    ```

    **输出**

    ```
    000013

    ```

*   **%j:** Displays number of the day in the year, from 001 to 366.

    ```
    import datetime

    x = datetime.datetime(2018, 5, 12, 2, 25, 50, 13)
    print(x.strftime("%f"))
    ```

    **输出**

    ```
    132

    ```

**从字符串到日期的转换**

在处理从 csv 导入的数据集或从网站表单获取输入时，需要多次从字符串到日期的转换。为此，python 提供了一个名为**str time()**的方法。

**语法:**

```
datetime.strptime(string, format)

```

**参数:**

*   **字符串–**输入字符串。
*   **格式–**这是字符串类型。即指令可以嵌入格式字符串中。

**示例:**

```
from datetime import datetime

print(datetime.strptime('5/5/2019',
                        '%d/%m/%Y'))
```

**输出**

```
2019-05-05 00:00:00

```