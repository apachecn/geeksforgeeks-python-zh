# Python | Decimal compare _ signal()方法

> 原文:[https://www . geesforgeks . org/python-decimal-compare _ signal-method/](https://www.geeksforgeeks.org/python-decimal-compare_signal-method/)

**十进制# compare _ signal():compare _ signal()**是一种十进制类方法，用于比较除 NaN 值之外的两个十进制值。

> **语法:**Decimal . compare _ signal()
> **参数:**十进制值
> **返回:**
> 1–如果 a>b
> -1–如果 a<b
> 0–如果 a = b

**代码# 1:compare _ signal()方法示例**

## 蟒蛇 3

```
# Python Program explaining
# compare_signal() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0.142857')

b = Decimal(-1)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare_signal() method
print ("\n\nDecimal a with compare_signal() method : ", a.compare_signal(a))

print ("Decimal a with compare_signal() method : ", a.compare_signal(b))

print ("Decimal b with compare_signal() method : ", b.compare_signal(a))
```

**输出:**

```
Decimal value a :  0.142857
Decimal value b :  -1

Decimal a with compare_signal() method :  0
Decimal a with compare_signal() method :  1
Decimal b with compare_signal() method :  -1
```

**代码# 2:compare _ signal()方法示例**

## 蟒蛇 3

```
# Python Program explaining
# compare_signal() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare_signal() method
print ("\n\nDecimal a with compare_signal() method : ", a.compare_signal(a))

print ("Decimal a with compare_signal() method : ", a.compare_signal(b))

print ("Decimal b with compare_signal() method : ", b.compare_signal(a))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with compare_signal() method :  0
Decimal a with compare_signal() method :  -1
Decimal b with compare_signal() method :  1
```