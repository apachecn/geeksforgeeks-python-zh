# 将 Python 日期时间转换为纪元

> 原文:[https://www . geesforgeks . org/convert-python-datetime-to-epoch/](https://www.geeksforgeeks.org/convert-python-datetime-to-epoch/)

在本文中，我们将讨论将 Python 日期时间转换为纪元的各种方法。纪元时间也称为 POSIX 时间，它将指示从 1970 年 1 月 1 日 00:00:00(世界协调时)开始经过的秒数，在大多数 windows 和 Unix 系统中。

**注意:** Epoch 依赖于平台，这意味着它取决于您正在使用的系统或操作系统。

日期时间是给定格式的时间

> 年/月/日/小时/分/秒:毫秒

## 方法一:使用[str time()](https://www.geeksforgeeks.org/python-strftime-function/)

strftime()用于将字符串 DateTime 转换为 DateTime。它也用于将日期时间转换为纪元。我们可以从 strftime()的 DateTime 中获取 epoch。

> **语法：** datetime.datetime（timestamp）.strftime（'%s'）
> 
> **参数:**
> 
> *   时间戳是输入的日期时间
> *   $s 用于获取纪元字符串
> *   日期时间是模块

参数%s 是一个平台相关的格式代码，它在 Linux 上工作。在 windows 中，相同的代码可以修改为由%S 代替%s 运行。

**示例:**使用 strftime 将日期时间转换为纪元的 Python 代码

## 蟒蛇 3

```
# import datetime module
import datetime

# convert datetime to epoch using strftime from
# time stamp 2021/7/7/1/2/1
# for linux:
epoch = datetime.datetime(2021, 7, 7, 1, 2, 1).strftime('%s')
# for windows:
# epoch = datetime.datetime(2021, 7,7 , 1,2,1).strftime('%S')
print(epoch)

# convert datetime to epoch using strftime from
# time stamp 2021/3/3/4/3/4
epoch = datetime.datetime(2021, 3, 3, 4, 3, 4).strftime('%s')
print(epoch)

# convert datetime to epoch using strftime from
# time stamp 2021/7/7/12/12/34
epoch = datetime.datetime(2021, 7, 7, 12, 12, 34).strftime('%s')
print(epoch)

# convert datetime to epoch using strftime from 
# time stamp 2021/7/7/12/56/00
epoch = datetime.datetime(2021, 7, 7, 12, 56, 0).strftime('%s')
print(epoch)
```

**Output**

```
1625619721
1614744184
1625659954
1625662560

```

## 方法 2:使用时间戳()

我们可以使用 timestamp()从 DateTime 中获取 epoch。

> **语法:** datetime.datetime(时间戳)。时间戳()
> 
> **参数:**
> 
> *   日期时间是模块
> *   时间戳是输入的日期时间

**示例:**使用时间戳()将 DateTime 转换为 epoch 的 Python 代码

## 蟒蛇 3

```
# import datetime module
import datetime

# convert datetime to epoch using timestamp()
# from time stamp 2021/7/7/0/0/0
epoch = datetime.datetime(2021, 7, 7, 0, 0, 0).timestamp()
print(epoch)

# convert datetime to epoch using timestamp()
# from time stamp 2021/3/3/4/3/4
epoch = datetime.datetime(2021, 3, 3, 4, 3, 4).timestamp()
print(epoch)

# convert datetime to epoch using timestamp()
# from time stamp 2021/7/7/12/12/34
epoch = datetime.datetime(2021, 7, 7, 12, 12, 34).timestamp()
print(epoch)

# convert datetime to epoch using timestamp()
# from time stamp 2021/7/7/12/56/00
epoch = datetime.datetime(2021, 7, 7, 12, 56, 00).timestamp()
print(epoch)
```

**Output**

```
1625616000.0
1614744184.0
1625659954.0
1625662560.0

```