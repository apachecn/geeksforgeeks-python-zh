# Python–从年和工作日获取月份

> 原文:[https://www . geeksforgeeks . org/python-按年按月获取工作日/](https://www.geeksforgeeks.org/python-get-month-from-year-and-weekday/)

给定一年和一个工作日，任务是编写一个 Python 程序来获得一个月和一周。

**示例:**

```py
Input : test_year = 1997, test_week = 27
Output : 1997-07-07 00:00:00
Explanation : 27th Week starts from 7 july in 1997.

Input : test_year = 2021, test_week = 27
Output : 2021-07-05 00:00:00
Explanation : 27th Week starts from 5 july in 2021.
```

**方法#1:使用%W、%w**

用%W 解析日期会将我们设置为一周的开始，此外，%w 获取所需的工作日，我们将使用默认值 1。可以根据要求进行调整。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Start week from year and weekday
# Using %W, %w
from datetime import datetime, timedelta

# initializing year
test_year = 1997

# initializing week
test_week = 27

# printing original date
print("The original year, week is : " + str(test_year) + " " + str(test_week))

date = str(test_year) + '-W' + str(test_week)

# getting date
res = datetime.strptime(date + '-1', "%Y-W%W-%w")

# printing result
print("The starting date of week : " + str(res))
```

**输出:**

```py
The original year, week is : 1997 27
The starting date of week : 1997-07-07 00:00:00
```

**方法 2:使用 relativedelta()**

这只是将所需的周数添加到所需的年份中，并获得所需的初始日期。这增加了星期，因此可以根据一年的开始日期给出任何工作日。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Start week from year and weekday
# Using relativedelta()
import datetime
from dateutil.relativedelta import relativedelta

# initializing year
test_year = 1997

# initializing week
test_week = 27

# printing original date
print("The original year, week is : " + str(test_year) + " " + str(test_week))

# contructing date
date = datetime.date(test_year, 1, 1)

# getting date by adding weeks to year beg. 
# prints 9 July. as 1 jan was wednesday, 27th 
# weeks beginning is from wed.
res = date + relativedelta(weeks = +test_week)

# printing result
print("The starting date of week : " + str(res))
```

**输出:**

```py
The original year, week is : 1997 27
The starting date of week : 1997-07-09
```