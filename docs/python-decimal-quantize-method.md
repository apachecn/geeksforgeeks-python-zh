# Python |十进制量化()方法

> 原文:[https://www . geesforgeks . org/python-decimal-quantize-method/](https://www.geeksforgeeks.org/python-decimal-quantize-method/)

**Decimal # quantize():quantize()**是一个 Decimal 类方法，它返回一个等于第一个十进制值(四舍五入)的值，该值具有第二个十进制值的指数。

> **语法:**十进制.量化()
> 
> **参数:**十进制值
> 
> **返回:**等于第一个十进制值(四舍五入)的值，其指数为第二个十进制值。

**代码#1:量化()方法示例**

```py
# Python Program explaining 
# quantize() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.quantize() method
print ("\n\nDecimal a with quantize() method : ", a.quantize(b))

print ("Decimal b with quantize() method : ", b.quantize(b))
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with quantize() method :  -1.000000
Decimal b with quantize() method :  0.142857

```

**代码#2:量化()方法示例**

```py
# Python Program explaining 
# quantize() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.quantize() method
print ("\n\nDecimal a with quantize() method : ", a.quantize(b))

print ("Decimal b with quantize() method : ", b.quantize(b))
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with quantize() method :  -0E+5
Decimal b with quantize() method :  3.21E+7

```