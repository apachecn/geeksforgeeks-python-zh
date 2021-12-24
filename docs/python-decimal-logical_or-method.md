# Python | Decimal logic _ or()方法

> 原文:[https://www . geesforgeks . org/python-decimal-logic _ or-method/](https://www.geeksforgeeks.org/python-decimal-logical_or-method/)

**十进制# logic _ or():logic _ or()**是一个十进制类方法，它返回两个十进制值的数字或。

> **语法:**decimal . logic _ or()
> 
> **参数:**十进制值
> 
> **返回:**两位(逻辑)十进制值的数字或。

**代码#1:逻辑 _or()方法示例**

```py
# Python Program explaining 
# logical_or() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0')

b = Decimal('1')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_or() method
print ("\n\nDecimal a with logical_or() method : ", a.logical_or(b))

print ("Decimal b with logical_or() method : ", b.logical_or(b))
```

**输出:**

```py
Decimal value a :  0
Decimal value b :  1

Decimal a with logical_or() method :  1
Decimal b with logical_or() method :  1

```

**代码#2:逻辑 _or()方法示例**

```py
# Python Program explaining 
# logical_or() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('1')

b = Decimal('0')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_or() method
print ("\n\nDecimal a with logical_or() method : ", a.logical_or(a))

print ("Decimal b with logical_or() method : ", a.logical_or(b))
```

**输出:**

```py
Decimal value a :  1
Decimal value b :  0

Decimal a with logical_or() method :  1
Decimal b with logical_or() method :  1

```