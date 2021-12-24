# Python 中 Datetime.date 类的 from 序数()函数

> 原文:[https://www . geesforgeks . org/from 序数-日期时间函数-日期时间类-在 python 中/](https://www.geeksforgeeks.org/fromordinal-function-of-datetime-date-class-in-python/)

**from 序数()**函数用于返回指定公历序数对应的公历日期。这与用于将公历日期转换为公历序数的 toordinal()函数相反。当一个负的序数值或超出 date.max.toordinal()返回的值的序数被传递给 toordinal()函数的参数时，该函数会引发 ValueError。

> **语法:**@ class method from 序数(序数)
> 
> **参数:**该函数接受如下所示的参数:
> 
> *   **序数:**这是指定的公历序数，将为其找到公历日期。
> 
> **返回值:**该函数返回指定公历序数对应的公历日期。

**例 1:出自**T2【具体 T4【日】的 **公历。**

## 蟒蛇 3

```
# Python3 code for getting
# the Gregorian date corresponding
# to a given Gregorian ordinal.

# Importing datetime module
import datetime

# Specifying a Gregorian ordinal
ordinal = 123456;

# Calling the fromordinal() function
# over the specified Gregorian ordinal
date = datetime.date.fromordinal(ordinal);

# Printing the Gregorian date
print("The Gregorian date for the Gregorian\
ordinal %d is: %s"%(ordinal, date));
```

**输出:**

```
The Gregorian date for the Gregorian ordinal 123456 is: 0339-01-05
```

**例 2:从公历第一**日**日**日**日算起。**

## 蟒蛇 3

```
# Python3 code for getting
# the Gregorian date corresponding
# to a given Gregorian ordinal.

# Importing datetime module
import datetime

# Calling the fromordinal() function over
# the 1st day of Gregorian calendar as its parameter
date = datetime.date.fromordinal(1);

# Printing the Gregorian date for the 1st date
# of Gregorian calendar
print("Gregorian Date for the 1st day \
of Gregorian calendar: %s"%date);
```

**输出:**

```
Gregorian Date for the 1st day of Gregorian calendar: 0001-01-01
```