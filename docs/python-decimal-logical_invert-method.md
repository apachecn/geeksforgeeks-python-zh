# Python | Decimal logic _ invert()方法

> 原文:[https://www . geesforgeks . org/python-decimal-logic _ invert-method/](https://www.geeksforgeeks.org/python-decimal-logical_invert-method/)

**Decimal # logic _ invert():logic _ invert()**是一个 Decimal 类方法，返回 Decimal 值的数字反转。

> **语法:**decimal . logic _ invert()
> 
> **参数:**十进制值
> 
> **返回:**十进制值的数字反转。

**代码# 1:logic _ invert()方法示例**

```py
# Python Program explaining 
# logical_invert() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0')

b = Decimal('1')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_invert() method
print ("\n\nDecimal a with logical_invert() method : ", a.logical_invert())

print ("Decimal b with logical_invert() method : ", b.logical_invert())
```

**输出:**

```py
Decimal value a :  0
Decimal value b :  1

Decimal a with logical_invert() method :  1111111111111111111111111111
Decimal b with logical_invert() method :  1111111111111111111111111110

```

**代码# 2:logic _ invert()方法示例**

```py
# Python Program explaining 
# logical_invert() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('1')

b = Decimal('0')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_invert() method
print ("\n\nDecimal a with logical_invert() method : ", a.logical_invert())

print ("Decimal b with logical_invert() method : ", a.logical_invert())
```

**输出:**

```py
Decimal value a :  1
Decimal value b :  0

Decimal a with logical_invert() method :  1111111111111111111111111110
Decimal b with logical_invert() method :  1111111111111111111111111110

```