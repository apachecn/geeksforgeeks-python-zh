# 在 Python3 中转换字符串为双精度

> 原文:[https://www . geesforgeks . org/convert-string-to-double-in-python 3/](https://www.geeksforgeeks.org/convert-string-to-double-in-python3/)

给定一个字符串，我们的任务是将其转换为双精度。因为双数据类型允许数字具有非整数值。所以字符串到 double 的转换和字符串到 float 的转换是一样的

这可以通过以下两种方式实现

**1)使用浮动()方法**

## 蟒蛇 3

```
str1 = "9.02"
print("This is the initial string: " + str1)

# Converting to double
str2 = float(str1)
print("The conversion of string to double is", str2)

str2 = str2+1
print("The converted string to double is incremented by 1:", str2)
```

**输出:**

```
This is the initial string: 9.02
The conversion of string to double is 9.02
The converted string to double is incremented by 1: 10.02
```

**2)使用 decimal()方法:**因为我们只需要一个带有十进制数值的字符串，所以也可以使用这个方法

## 蟒蛇 3

```
from decimal import Decimal

str1 = "9.02"
print("This is the initial string: " + str1)

# Converting to double
str2 = Decimal(str1)
print("The conversion of string to double is", str2)

str2 = str2+1
print("The converted string to double is incremented by 1:", str2)
```

**输出:**

```
This is the initial string: 9.02
The conversion of string to double is 9.02
The converted string to double is incremented by 1: 10.02
```