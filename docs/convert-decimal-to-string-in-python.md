# 在 Python 中将十进制转换为字符串

> 原文:[https://www . geesforgeks . org/convert-十进制到 python 中的字符串/](https://www.geeksforgeeks.org/convert-decimal-to-string-in-python/)

Python 定义了类型转换函数，直接将一种数据类型转换成另一种数据类型。本文旨在提供有关将十进制转换为字符串的信息。

## 将十进制转换为字符串

str()方法可用于在 Python 中将小数转换为字符串。

> **语法:** str(对象，编码='utf-8？，错误= '严格')
> 
> **参数:**
> 
> **对象:**要返回字符串表示的对象。
> 
> **编码:**给定对象的编码。
> 
> **错误:**解码失败时的响应。

**例 1:**

## 蟒蛇 3

```
from decimal import Decimal

dec = Decimal(10)
print(dec, type(dec))

# Converting to string
dec = str(dec)
print(dec, type(dec))
```

**输出:**

```
10 <class 'decimal.Decimal'>
10 <class 'str'>
```

**例 2:**

## 蟒蛇 3

```
from decimal import Decimal

dec = Decimal("0.01")
print(dec, type(dec))

# Converting decimal to string
s = str(dec)
print(s, type(dec))
```

**输出:**

```
0.01 <class 'decimal.Decimal'>
0.01 <class 'decimal.Decimal'>
```