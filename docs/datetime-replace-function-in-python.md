# Python 中的 Datetime.replace()函数

> 原文:[https://www . geesforgeks . org/datetime-replace-function-in-python/](https://www.geeksforgeeks.org/datetime-replace-function-in-python/)

**Datetime.replace()** 函数用于用给定的参数替换 Datetime 对象的内容。

> **语法:** Datetime_object.replace(年、月、日、时、分、秒、微秒、tzinfo)
> 
> **参数:**
> 
> *   **年份:**范围内的新年值-[1，9999]，
> *   **月:**范围内的新月值-[1，12]，
> *   **日:**范围内的新日值-[1，31]，
> *   **小时:**范围内的新小时值-[24]，
> *   **分钟:**范围内的新分钟值-[60]，
> *   **秒:**范围内的新秒值-[60]，
> *   **微秒:**范围内新的微秒值-[1000000]，
> *   **tzinfo:** 新时间区信息。
> 
> **返回:**返回修改后的日期时间对象

**注:**

*   在 replace()中，我们只能传递 DateTime 对象已经拥有的参数，替换 DateTime 对象中不存在的参数将引发错误
*   它不会替换原始的日期时间对象，但会返回修改后的日期时间对象

**例 1:** 将当前日期的年份替换为 2000 年。

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Getting current date using today()
# function of the datetime class
todays_date = datetime.date.today()
print("Original Date:", todays_date)

# Replacing the todays_date year with
# 2000 using replace() function
modified_date = todays_date.replace(year=2000)
print("Modified Date:", modified_date)
```

**输出:**

```py
Original Date: 2021-07-27
Modified Date: 2000-07-27
```

**示例 2:** 替换日期时间对象中不存在的参数。

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Getting current date using today()
# function of the datetime class
todays_date = datetime.date.today()
print("Original Date:", todays_date,)

# Trying to replace the todays_date hour
# with 3 using replace() function
modified_date = todays_date.replace(hour=3)
print("Modified Date:", modified_date)
```

**输出:**

> 追溯(最近一次通话持续时间):
> 
> 文件“/home/6e 1 aaed 34d 749 F5 f15 af 6 DC 27 ce 73 a 2d . py”，第 9 行，在“<module>”中</module>
> 
> modified _ date = today _ date . replace(小时=3)
> 
> 类型错误:“小时”是此函数的无效关键字参数

因此，我们观察到，我们得到一个错误，因为小时不在 datetime 对象中。现在我们将创建一个带有 hour 属性的 datetime 对象，并尝试将其更改为 03，我们还将日期更改为 10。

## 蟒蛇 3

```py
# importing the datetime module
import datetime

# Getting current date and time using now()
# function of the datetime class
todays_date = datetime.datetime.now()
print("Today's date and time:", todays_date)

# Replacing todays_date hour with 3 and day
# with 10 using replace() function using hour
# and day parameter
modified_date = todays_date.replace(day = 10, hour=3)
print("Modified date and time:", modified_date)
```

**输出:**

```py
Today's date and time: 2021-07-28 09:08:47.563144
Modified date and time: 2021-07-10 03:08:47.563144
```