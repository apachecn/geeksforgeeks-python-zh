# 在 Python 中创建日期范围列表

> 原文:[https://www . geeksforgeeks . org/创建 python 中的日期范围列表/](https://www.geeksforgeeks.org/creating-a-list-of-range-of-dates-in-python/)

给定一个日期，任务是编写一个 Python 程序来创建一个日期范围列表，其中下一个 K 日期从当前日期开始。

**示例:**

> **输入 ：** test_date = datetime.datetime（1997， 1， 4）， K = 5
> 
> **输出 ：** [datetime.datetime（1997， 1， 4， 0， 0）， datetime.datetime（1997， 1， 5， 0， 0）， datetime.datetime（1997， 1， 6， 0， 0）， datetime.datetime（1997， 1， 7， 0， 0）， datetime.datetime（1997， 1， 8， 0， 0）]
> 
> **说明:**列表中提取 1 月 4 日后的 5 个日期。
> 
> **输入 ：** test_date = datetime.datetime（1997， 1， 4）， K = 4
> 
> **输出 ：** [datetime.datetime（1997， 1， 4， 0， 0）， datetime.datetime（1997， 1， 5， 0， 0）， datetime.datetime（1997， 1， 6， 0， 0）， datetime.datetime（1997， 1， 7， 0， 0）]
> 
> **说明:**列表中提取 1 月 4 日后的 4 个日期。

### **方法一:使用** [**时间增量()**](https://www.geeksforgeeks.org/python-datetime-timedelta-function/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们可以使用 timedelta()每天添加连续的 delta，使用列表理解来迭代所需的大小并构造所需的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get Construct Next K dates List
# Using timedelta() + list comphehension
import datetime

# initializing date
test_date = datetime.datetime(1997, 1, 4)

# printing original date
print("The original date is : " + str(test_date))

# initializing K 
K = 5

# timedelta() gets successive dates with 
# appropriate difference
res = [test_date + datetime.timedelta(days=idx) for idx in range(K)]

# printing result
print("Next K dates list : " + str(res))
```

**输出:**

> 原日期为:1997-01-04 00:00:00
> 
> 下一个 K 日期列表 ： [datetime.datetime（1997， 1， 4， 0， 0）， datetime.datetime（1997， 1， 5， 0， 0），
> 
> datetime.datetime（1997， 1， 6， 0， 0）， datetime.datetime（1997， 1， 7， 0， 0）， datetime.datetime（1997， 1， 8， 0， 0）]

### **方法 2:使用** [**计数()**](https://www.geeksforgeeks.org/python-list-function-count/) **+** [**发生器功能**](https://www.geeksforgeeks.org/generators-in-python/)

在这种情况下，我们执行与上述函数类似的任务，使用生成器来执行日期序列任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get Construct Next K dates List
# Using count() + generator function
import datetime
import itertools

# initializing date
test_date = datetime.datetime(1997, 1, 4)

# printing original date
print("The original date is : " + str(test_date))

# initializing K 
K = 5

# timedelta() gets successive dates with 
# appropriate difference
gen_fnc = (
  test_date - datetime.timedelta(days=idx) for idx in itertools.count())

# islice passes counter
res = itertools.islice(gen_fnc, K)

# printing result
print("Next K dates list : " + str(list(res)))
```

**输出:**

> 原日期为:1997-01-04 00:00:00
> 
> Next K dates list ： [datetime.datetime（1997， 1， 4， 0， 0）， datetime.datetime（1997， 1， 3， 0， 0），
> 
> datetime.datetime（1997， 1， 2， 0， 0）， datetime.datetime（1997， 1， 1， 0， 0）， datetime.datetime（1996， 12， 31， 0， 0）]