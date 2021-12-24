# Python | Decimal normalize()方法

> 原文:[https://www . geesforgeks . org/python-decimal-normalize-method/](https://www.geeksforgeeks.org/python-decimal-normalize-method/)

**Decimal # normalize():normalize()**是一个 Decimal 类方法，返回 Decimal 值的最简单形式。

```py
Syntax:  Decimal.normalize()

Parameter:  Decimal values

Return:  the simplest form of the Decimal value. 

```

**代码# 1:normalize()方法示例**

```py
# Python Program explaining 
# normalize() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.normalize() method
print ("\n\nDecimal a with normalize() method : ", a.normalize())

print ("Decimal b with normalize() method : ", b.normalize())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with normalize() method :  -1
Decimal b with normalize() method :  0.142857

```

**代码# 2:normalize()方法示例**

```py
# Python Program explaining 
# normalize() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.normalize() method
print ("\n\nDecimal a with normalize() method : ", a.normalize())

print ("Decimal b with normalize() method : ", b.normalize())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with normalize() method :  -3.14
Decimal b with normalize() method :  3.21E+7

```