# 使用 Python 获取当前日期和时间

> 原文:[https://www . geesforgeks . org/get-current-date-time-use-python/](https://www.geeksforgeeks.org/get-current-date-and-time-using-python/)

**先决条件:** [日期时间模块](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

在这个例子中，我们将学习如何使用 Python 获取当前日期和时间。

在 Python 中，日期和时间本身不是一种数据类型，但是可以导入一个名为`datetime`的模块来处理日期和时间。Datetime 模块内置于 Python 中，无需外部安装。

使用`datetime`模块的`datetime.now()`功能获取当前日期和时间。该函数返回当前的本地日期和时间。

> **语法:** datetime.now(tz)
> 
> **参数:**
> **tz :** 需要当前时间和日期的指定时区。(默认使用格林威治子午线时间。)
> 
> **返回:**以时间格式返回当前日期和时间。

**例 1:**

```py
# Python3 code to demonstrate 
# Getting current date and time using  
# now(). 

# importing datetime module for now() 
import datetime 

# using now() to get current time 
current_time = datetime.datetime.now() 

# Printing value of now. 
print ("Time now at greenwich meridian is : "
                                    , end = "") 
print (current_time) 
```

**输出:**

```py
Time now at greenwich meridian is : 2019-12-11 13:54:30.967356

```

**now()的属性:**

`now()`有不同的属性，与年、月、日、时、分、秒等时间属性相同。

**例 2:**

```py
# Python3 code to demonstrate 
# attributes of now() 

# importing datetime module for now() 
import datetime 

# using now() to get current time 
current_time = datetime.datetime.now() 

# Printing attributes of now(). 
print ("The attributes of now() are : ") 

print ("Year : ", end = "") 
print (current_time.year) 

print ("Month : ", end = "") 
print (current_time.month) 

print ("Day : ", end = "") 
print (current_time.day) 

print ("Hour : ", end = "") 
print (current_time.hour) 

print ("Minute : ", end = "") 
print (current_time.minute) 

print ("Second : ", end = "") 
print (current_time.second) 

print ("Microsecond : ", end = "") 
print (current_time.microsecond) 
```

**输出:**

```py
The attributes of now() are : 
Year : 2019
Month : 12
Day : 11
Hour : 13
Minute : 56
Second : 7
Microsecond : 292616

```

**获取特定时区的时间:**

在上面的例子中，可以看到上面的代码没有给出时区的当前日期和时间。获取特定时区的日期和时间`now()`将时区作为输入，给出面向时区的输出时间。但是这些时区是在 T2 图书馆定义的。

**例:3**

```py
# Python3 code to demonstrate 
# attributes of now() for timezone 

# for now() 
import datetime 

# for timezone() 
import pytz 

# using now() to get current time 
current_time = datetime.datetime.now(pytz.timezone('Asia/Kolkata')) 

# printing current time in india 
print ("The current time in india is : ") 
print (current_time)  
```

**输出:**

```py
The current time in india is : 
2019-12-11 19:28:23.973616+05:30

```