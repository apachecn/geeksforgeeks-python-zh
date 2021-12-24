# jdcal 模块介绍

> 原文:[https://www.geeksforgeeks.org/introduction-to-jdcal-module/](https://www.geeksforgeeks.org/introduction-to-jdcal-module/)

Python 有一个将儒略历转换为公历的包，叫做 [jdcal](https://pypi.org/project/jdcal/) 。它大大简化了两个系统之间的转换，只需几行代码就足以实现该功能。

jdcal 中主要有四个功能:

*   **gcal2jd:** Convert the Gregorian calendar to Julian day. Take year, month and day as integer parameters and return 2 floating-point tuples.
*   **JD2cal:** Convert Julian Day into Gregorian calendar. Take two integers as parameters, and return a four-element tuple containing year (int), month (int), day (int) and the decimal part of Gregorian calendar day (float).
*   **JCA L2J D:** Convert the julian calendar date to the julian calendar date. Take all integer values as args arrays and return a floating-point tuple.
*   **jd2jcal:** Convert the julian calendar date to a given Julian day. Returns a tuple of four elements containing year (int), month (int), day (int) and decimal part of day in julian calendar (floating point) format.

**安装:**

要安装，请在您的终端中运行以下命令

```
pip install jdcal

```

**实施:**

**例 1:** (gcal2jd)

## 蟒 3

```
# import module
import jdcal as j

# declare function
a= j.gcal2jd(2020, 12, 15) 
print(a) 
```

**输出:**

> (2400000.5，59198.0)

**例 2**:(jd2 cal)

## 蟒 3

```
# import module
import jdcal as j

# declare function
b= j.jd2gcal(2400000.5, 59198.0)

print(b)
```