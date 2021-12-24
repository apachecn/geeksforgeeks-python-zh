# 使用 Python 获取昨天的日期

> 原文:[https://www . geesforgeks . org/get-yesterdays-date-use-python/](https://www.geeksforgeeks.org/get-yesterdays-date-using-python/)

**先决条件:** [日期时间模块](https://www.geeksforgeeks.org/python-datetime-module-with-examples/#date)
在 Python 中，日期和时间本身不是一种数据类型，但是可以导入一个名为 datetime 的模块来处理日期和时间。Datetime 模块内置于 Python 中，无需外部安装。

为了处理日期，datetime 模块提供了日期类，timedelta 类用于计算日期差异。让我们看看他们。

*   **日期类:**当这个类的一个对象被实例化时，它表示一个格式为 YYYY-MM-DD 的日期。使用 date 类的 today()函数返回当前的本地日期。today()函数带有几个属性(年、月和日)。这些可以单独打印。
    **语法:**

```
date.today()
```

*   **Timedelta 类:** Python [timedelta()](https://www.geeksforgeeks.org/python-datetime-module-with-examples/#timedelta) 函数存在于 datetime 库下，datetime 库一般是**用来计算日期差异**的，也可以用于 Python 中的日期操作。这是执行日期操作最简单的方法之一。
    **语法:**

```
datetime.timedelta(days=0, seconds=0, microseconds=0,
                milliseconds=0, minutes=0, hours=0, weeks=0)

Returns: Date
```

下面是实现

## 蟒蛇 3

```
# Python program to get
# Yesterday's date

# Import date and timedelta class
# from datetime module
from datetime import date
from datetime import timedelta

# Get today's date
today = date.today()
print("Today is: ", today)

# Yesterday date
yesterday = today - timedelta(days = 1)
print("Yesterday was: ", yesterday)
```

**输出:**

```
Today is:  2019-12-11
Yesterday was:  2019-12-10
```

你只需要用“时间增量”减去你想要返回的天数，就可以得到过去的日期。

例如，减去二，我们将得到前天的日期。

## 蟒蛇 3

```
# Python program to get
# Yesterday's date

# Import date and timedelta class
# from datetime module
from datetime import date
from datetime import timedelta

# Get today's date
today = date.today()
print("Today is: ", today)

# Get 2 days earlier
yesterday = today - timedelta(days = 2)
print("Day before yesterday was: ", yesterday)
```

**输出:**

```
Today is:  2019-12-11
Day before yesterday was:  2019-12-09
```