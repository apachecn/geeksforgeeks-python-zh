# Python 统计中的 fmean()函数

> 原文:[https://www . geesforgeks . org/fmean-python 中的函数-统计/](https://www.geeksforgeeks.org/fmean-function-in-python-statistics/)

Python 3.8 的统计模块提供了一个函数 **fmean()** ，该函数将所有数据转换为浮点数据类型，然后计算以序列或可迭代形式提供的数据的算术平均值或平均值。这个函数的输出总是一个浮点数。
使用 mean()和 fmean()计算平均值的唯一区别在于，使用 fmean()时，数据会转换为浮点数，而在 mean()的情况下，数据不会转换为浮点数。此外，fmean()函数比 mean()函数运行得更快。

> **语法:**fmean([数据集}])
> 
> **参数:**【数据集】:一组数字的列表或元组。
> 
> **返回:**所提供数据的浮点算术平均值。
> 
> **异常:**统计错误。当数据集为空时引发

**代码# 1:**fmean()的演示

```py
# Python program to demonstrate fmean() 

import statistics 

# list of numbers 
data = [1.8, 3.8, 4, 5.8, 7, 9.6, 2.4] 

fm = statistics.fmean(data) 

# Printing the floating-point mean 
print("Floating Point Mean is :", fm) 
```

**输出:**

```py
Floating Point Mean is: 4.914285714285714

```

**代码# 2:**fmean()的演示

```py
# Python program to demonstrate fmean() 

from statistics import fmean 

# tuple of positive numbers 
A1 = (11.4, 3.7, 4, 5, 7.9, 9.4, 2) 

# tuple of negative numbers
A2 = (-1.9, -2.8, -4, -7.5, -12.2, -19) 

# tuple of a mixed range of numbers 
A3 = (-1.9, -13.8, -6, 4.2, 5.9, 9.1) 

# dictionary of a set of values
# keys are taken in consideration by fmean() 
A4 = {1.1:"one.one", 2.8:"two.eight", 3:"three"} 

# Printing the mean of A1, A2, A3, A4
print("Floating Point Mean of A1 is", fmean(A1))
print("Floating Point Mean of A2 is", fmean(A2))
print("Floating Point Mean of A3 is", fmean(A3))
print("Floating Point Mean of A4 is", fmean(A4))
```

**输出:**

```py
Floating Point Mean of A1 is 6.2
Floating Point Mean of A2 is -7.8999999999999995
Floating Point Mean of A3 is -0.41666666666666674
Floating Point Mean of A4 is 2.3000000000000003

```

**代码 #3：** 统计错误

```py
# Python3 code to demonstrate StatisticsError

from statistics import fmean 

data =[]
print(fmean(data))  
```

**输出:**

> 回溯(最近一次调用最后一次):
> 文件“”，第 1 行，在
> 文件“C:\ user \ Admin \ AppData \ Local \ Programs \ Python \ Python 38-32 \ lib \ statistics。
> py，第 345 行，在 fmean
> 中从 None
> 统计中提升 StatisticsError(【fmean 至少需要一个数据点】)。统计错误:fmean 至少需要一个数据点

**应用:**
fmean()的应用类似于 mean()，虽然 fmean()相对比 mean()快。fmean()仅在需要计算数据的浮点平均值时使用，否则，为了计算样本的平均值，mean()是首选。由于 fmean()将其数据转换为浮点数，因此会产生更准确的结果。