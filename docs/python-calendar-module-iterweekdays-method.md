# Python 日历模块:iterweekdays()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-ITER weekdays-method/](https://www.geeksforgeeks.org/python-calendar-module-iterweekdays-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

**iterweekdays()** 方法返回一周将使用的星期几的迭代器。迭代器中的第一个数字将与 firstweekday()返回的数字相同。

```py
Syntax: iterweekdays()
Parameter: no parameter
Returns: iterator for the week day numbers
```

**代码#1:**

```py
# Python program to demonstrate working
# of iterweekdays() method

# importing calendar module
import calendar

# providing firstweekday = 0
obj = calendar.Calendar(firstweekday = 0)

for day in obj.iterweekdays():
    print(day)
```

**输出:**

```py
0
1
2
3
4
5
6
```

**代码#2:**

```py
# Python program to demonstrate working
# of iterweekdays() method

# importing calendar module
import calendar

# providing firstweekday = 2
obj = calendar.Calendar(firstweekday = 2)

for day in obj.iterweekdays():
    print(day)
```

**输出:**

```py
2
3
4
5
6
0
1
```