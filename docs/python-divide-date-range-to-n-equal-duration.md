# Python–将日期范围划分为 N 个相等的持续时间

> 原文:[https://www . geesforgeks . org/python-divide-date-range-to-n-equal-duration/](https://www.geeksforgeeks.org/python-divide-date-range-to-n-equal-duration/)

给定两个日期，任务是将其划分为相等的持续时间，并获得每个划分点的准确时间。

> **输入 ：** test_date1 = datetime.datetime（1997， 1， 4）， test_date2 = datetime.datetime（1997， 1， 30） N = 7
> 
> **输出 ：** [datetime.datetime（1997， 1， 4， 0， 0）， datetime.datetime（1997， 1， 7， 17， 8， 34， 285714）， datetime.datetime（1997， 1， 11， 10， 17， 8， 571428）， datetime.datetime（1997， 1， 15， 3， 25， 42， 857142）， datetime.datetime（1997， 1， 18， 20， 34， 17， 142856）， datetime.datetime（1997， 1997， 1， 22， 13， 42， 51， 428570）， datetime.datetime（1997， 1， 26， 6， 51， 25， 714284)]
> 
> **说明:**返回大小为 7 的日期列表，每个日期之间具有相等的增量。
> 
> **输入 ：** test_date1 = datetime.datetime（1997， 1， 4）， test_date2 = datetime.datetime（1997， 1， 30） N = 4
> 
> **输出 ：** [datetime.datetime（1997， 1， 4， 0， 0）， datetime.datetime（1997， 1， 10， 12， 0）， datetime.datetime（1997， 1， 17， 0， 0）， datetime.datetime（1997， 1， 23， 12， 0）]
> 
> **说明:**返回大小为 4 的日期列表，每个日期之间具有相等的增量。

**方法#1:使用循环**

在这种情况下，我们使用整个持续时间除以 n 来计算每个段持续时间。之后，每个日期都是使用循环中的段持续时间乘法来构建的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert date range to N equal durations
# Using loop
import datetime

# initializing dates
test_date1 = datetime.datetime(1997, 1, 4)
test_date2 = datetime.datetime(1997, 1, 30)

# printing original dates
print("The original date 1 is : " + str(test_date1))
print("The original date 2 is : " + str(test_date2))

# initializing N
N = 7

temp = []

# getting diff.
diff = ( test_date2 - test_date1) // N
for idx in range(0, N):

    # computing new dates
    temp.append((test_date1 + idx * diff))

# using strftime to convert to userfriendly 
# format
res = []
for sub in temp:
  res.append(sub.strftime("%Y/%m/%d %H:%M:%S"))

# printing result
print("N equal duration dates : " + str(res))
```

**输出:**

> 原日期 1 为:1997-01-04 00:00:00
> 
> 原日期 2 为:1997-01-30 00:00:00
> 
> n 相等的持续时间日期:['1997/01/04 00:00:00 '，' 1997/01/07 17:08:34 '，' 1997/01/11 10:17:08 '，' 1997/01/15 03:25:42 '，' 1997/01/18 20:34:17 '，' 1997/01/22 13:42:51 '，' 1997/18

**方法 2:使用** [**发电机功能**](https://www.geeksforgeeks.org/generators-in-python/)

在这种情况下，我们使用生成函数而不是循环方法来执行产生中间结果的任务。唯一不同的是返回中间结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert date range to N equal durations
# Using generator function
import datetime

def group_util(test_date1, test_date2, N):

    diff = (test_date2  - test_date1 ) / N
    for idx in range(N):

        # using generator function to solve problem
        # returns intermediate result
        yield (test_date1 + diff * idx)
    yield test_date2

# initializing dates
test_date1 = datetime.datetime(1997, 1, 4)
test_date2 = datetime.datetime(1997, 1, 30)

# printing original dates
print("The original date 1 is : " + str(test_date1))
print("The original date 2 is : " + str(test_date2))

# initializing N
N = 7

# calling generator expression
temp = list(group_util(test_date1, test_date2, N))

# using strftime to convert to userfriendly format
res = []
for sub in temp:
  res.append(sub.strftime("%Y/%m/%d %H:%M:%S"))

# printing result
print("N equal duration dates : " + str(res))
```

**输出:**

> 原日期 1 为:1997-01-04 00:00:00
> 
> 原日期 2 为:1997-01-30 00:00:00
> 
> n 相等的持续时间日期:['1997/01/04 00:00:00 '，' 1997/01/07 17:08:34 '，' 1997/01/11 10:17:08 '，' 1997/01/15 03:25:42 '，' 1997/01/18 20:34:17 '，' 1997/01/22 13:42:51 '，' 1997/18