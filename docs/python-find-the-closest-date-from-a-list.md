# Python–从列表中找到最近的日期

> 原文:[https://www . geesforgeks . org/python-从列表中找到最近的日期/](https://www.geeksforgeeks.org/python-find-the-closest-date-from-a-list/)

给定日期和日期列表，任务是编写一个 python 程序，在给定的输入日期列表中找到与输入日期最近的日期。

**示例:**

> **输入 ：** test_date_list = [datetime（2020， 4， 8）， datetime（2016， 8， 18）， datetime（2018， 9， 24）， datetime（2019， 6， 10）， datetime（2021， 8， 10）]， test_date = datetime（2017， 6， 6）
> 
> **产量:** 2016-08-18 00:00:00
> 
> **说明:**列表中距离 2017 年 6 月 6 日最近的日期为 2016 年 8 月 18 日。
> 
> **输入 ：** test_date_list = [datetime（2020， 4， 8）， datetime（2016， 8， 18）， datetime（2018， 9， 24）， datetime（2019， 6， 10）， datetime（2021， 8， 10）]， test_date = datetime（2016， 6， 6）
> 
> **产量:** 2016-08-18 00:00:00
> 
> **说明:**列表中距离 2016 年 6 月 6 日最近的日期为 2016 年 8 月 18 日。

### **方法一:使用**[**min()**](https://www.geeksforgeeks.org/max-min-python/)**+**[**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)**+**[**ABS()**](https://www.geeksforgeeks.org/abs-in-python/)

在这种情况下，使用 abs()将每个日期与给定日期的差值计算为关键字，将日期计算为值。min()用于获取最小键差，其值即为结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Nearest date in List
# Using min() + dictionary comprehension + abs()
from datetime import datetime

# initializing datelist
test_date_list = [datetime(2020, 4, 8), datetime(2016, 8, 18), 
                  datetime(2018, 9, 24), datetime(2019, 6, 10),
                  datetime(2021, 8, 10)]

# printing original list
print("The original list is : " + str(test_date_list))

# initializing test date 
test_date = datetime(2017, 6, 6)

# get all differences with date as values 
cloz_dict = { 
  abs(test_date.timestamp() - date.timestamp()) : date 
  for date in test_date_list}

# extracting minimum key using min()
res = cloz_dict[min(cloz_dict.keys())]

# printing result
print("Nearest date from list : " + str(res))
```

**输出:**

> 原始列表是：[datetime.datetime（2020， 4， 8， 0， 0）， datetime.datetime（2016， 8， 18， 0， 0）， datetime.datetime（2018， 9， 24， 0， 0）， datetime.datetime（2019， 6， 10， 0， 0）， datetime.datetime（2021， 8， 10， 0， 0）]
> 
> 离列表最近的日期:2016-08-18 00:00:00

### **方法 2:使用 min()+ABS()+**[T3】λT5】](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

解决这个问题的另一个更简单的方法是获取差异，并使用 min()捕获最小差异。这是一种灵活的方法，不仅可以扩展到日期时间，还可以扩展到所有数据类型。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Nearest date in List
# Using min() + abs() + lambda
from datetime import datetime

# initializing datelist
test_date_list = [datetime(2020, 4, 8), datetime(2016, 8, 18), 
                  datetime(2018, 9, 24), datetime(2019, 6, 10),
                  datetime(2021, 8, 10)]

# printing original list
print("The original list is : " + str(test_date_list))

# initializing test date 
test_date = datetime(2017, 6, 6)

# shorthand using lambda function for compact solution
res = min(test_date_list, key=lambda sub: abs(sub - test_date))

# printing result
print("Nearest date from list : " + str(res))
```

**输出:**

> 原始列表是： [datetime.datetime（2020， 4， 8， 0， 0）， datetime.datetime（2016， 8， 18， 0， 0），
> 
> datetime.datetime（2018， 9， 24， 0， 0）， datetime.datetime（2019， 6， 10， 0， 0）， datetime.datetime（2021， 8， 10， 0， 0）]
> 
> 离列表最近的日期:2016-08-18 00:00:00