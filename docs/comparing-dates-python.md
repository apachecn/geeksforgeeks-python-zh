# 在 Python 中比较日期

> 原文:[https://www.geeksforgeeks.org/comparing-dates-python/](https://www.geeksforgeeks.org/comparing-dates-python/)

在 Python 中，比较日期非常容易。使用比较运算符可以很容易地比较日期(如，<=,> =，！=等等。).让我们看看如何借助使用 Python 的 **`[datetime](https://www.geeksforgeeks.org/time-functions-python-set-2-date-manipulations/)`** 模块来比较日期。

**代码#1 :** 基本

```
# Simple Python program to compare dates

# importing datetime module
import datetime

# date in yyyy/mm/dd format
d1 = datetime.datetime(2018, 5, 3)
d2 = datetime.datetime(2018, 6, 1)

# Comparing the dates will return
# either True or False
print("d1 is greater than d2 : ", d1 > d2)
print("d1 is less than d2 : ", d1 < d2)
print("d1 is not equal to d2 : ", d1 != d2)
```

**输出:**

```
d1 is greater than d2 :  False
d1 is less than d2 :  True
d1 is not equal to d2 :  True
```

**代码#2 :** **整理日期**

对一组日期进行排序的最好方法之一是将它们存储到一个列表中，并应用`sort()`方法。这将对列表中所有可用的日期进行排序。可以使用`append()`方法将日期类对象存储到列表中。

```
# Python program to sort the dates

# importing datetime module
from datetime import *

# create empty list
group = []

# add today's date
group.append(date.today())

# create some more dates
d = date(2015, 6, 29)
group.append(d)

d = date(2011, 4, 7)
group.append(d)

# add 25 days to the date
# and add to the list
group.append(d + timedelta(days = 25))

# sort the list
group.sort()

# print the dates
for d in group:
    print(d)

```

**输出:**

```
2011-04-07
2011-05-02
2015-06-29
2018-05-24
```

**代码#3 :** **比较日期**

比较两个`date` 类对象，就像比较两个数字一样。

```
# importing datetime module
from datetime import *

# Enter birth dates and store
# into date class objects
d1, m1, y1 = [int(x) for x in input("Enter first"
        " person's date(DD/MM/YYYY) : ").split('/')]

b1 = date(y1, m1, d1)

# Input for second date
d2, m2, y2 = [int(x) for x in input("Enter second"
        " person's date(DD/MM/YYYY) : ").split('/')]

b2 = date(y2, m2, d2)

# Check the dates
if b1 == b2:
    print("Both persons are of equal age")

elif b1 > b2:
    print("The second person is older")

else:
    print("The first person is older")
```

**输出:**

```
Enter first person's date(DD/MM/YYYY) : *12/05/2017*
Enter second person's date(DD/MM/YYYY) : *10/11/2015*
The second person is older
```

=,>,>