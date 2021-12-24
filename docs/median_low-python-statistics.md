# Python 统计模块

中的中位数 _low()函数

> 原文:[https://www.geeksforgeeks.org/median_low-python-statistics/](https://www.geeksforgeeks.org/median_low-python-statistics/)

中值通常被称为中心位置的稳健度量，受数据中异常值的影响较小。

Python 中的**统计**模块允许三个选项来处理数据集中的中值/中间值元素，它们是`median(), median_low() and median_high()`。

*低中位数*永远是数据集中的一员。当数据点数为奇数时，返回中间值。当它为偶数时，返回两个中间值中较小的一个。让我们看看`**median_low()**` 是如何工作的。

> **`Syntax :`** **中值 _ 低(*【数据集】* )**
> 
> **`Parameters :`**
> **【数据集】**:接受列表、元组或可交互的数字数据集。
> 
> **`Returntype :`** 返回数值数据的低中值。低中位数是实际数据集的一个成员。
> 
> **`Exceptions :`** **统计当数据集为空时，会出现错误**。

**代码#1 :** 工作

```
# Python code to demonstrate the 
# working of median_low()

# importing the statistics module
import statistics

# simple list of a set of integers
set1 = [1, 3, 3, 4, 5, 7]

# Note: low median will always be
#        a member of the data-set.

# Print low median of the data-set
print("Low median of the data-set is % s " 
        % (statistics.median_low(set1)))
```

**输出:**

```
Low median of the data-set is 3 

```

**代码#2 :** 工作的中值 _ 低()和中值来区分它们。

```
# Python code to demonstrate the
# working of median_low()

# importing the statistics module
import statistics

# simple list of a set of integers
set1 = [1, 3, 3, 4, 5, 7]

# Print median of the data-set

# Median value may or may not
# lie within the data-set
print("Median of the set is % s" 
      % (statistics.median(set1)))

# Print low median of the data-set
print("Low Median of the set is % s " 
       % (statistics.median_low(set1)))
```

**输出:**

```
Median of the set is 3.5
Low Median of the set is 3 

```

**代码#3 :** 在不同范围的数据集上使用中值 _ 低()

```
# Python code to demonstrate the
# working of median_low()

# importing statistics module
from statistics import median_low

# Importing fractions module as fr
from fractions import Fraction as fr

# tuple of positive integer numbers
data1 = (2, 3, 4, 5, 7, 9, 11)

# tuple of a set of floating-point values
data2 = (2.4, 5.1, 6.7, 8.9)

# tuple of a set of fractional numbers
data3 = (fr(1, 2), fr(44, 12),
         fr(10, 3), fr(2, 3))

# tuple of a set of negative integers
data4 = (-5, -1, -12, -19, -3)

# tuple of set of positive
# and negative integers
data5 = (-1, -2, -3, -4, 4, 3, 2, 1)

# Print low_median() of given data-sets
print("Low Median of data-set 1 is % s" % (median_low(data1)))
print("Low Median of data-set 2 is % s" % (median_low(data2)))
print("Low Median of data-set 3 is % s" % (median_low(data3)))
print("Low Median of data-set 4 is % s" % (median_low(data4)))
print("Low Median of data-set 5 is % s" % (median_low(data5)))
```

**输出:**

```
Low Median of data-set 1 is 5
Low Median of data-set 2 is 5.1
Low Median of data-set 3 is 2/3
Low Median of data-set 4 is -5
Low Median of data-set 5 is -1

```

**代码#4 :** 提高统计错误

```
# Python code to demonstrate
# StatisticsError of median_low()

# importing the statistics module
from statistics import median_low

# creating an empty data-set
empty = []

# will raise StatisticsError
print(median_low(empty))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/5f3e758236f872d014f9d741743c30a4.py", line 10, in 
    print(median_low(empty))
  File "/usr/lib/python3.5/statistics.py", line 376, in median_low
    raise StatisticsError("no median for empty data")
statistics.StatisticsError: no median for empty data

```

**应用:**
**中值 _ 低()**用于数据离散且更希望中值是数据中的实际点而不是外推点的情况。