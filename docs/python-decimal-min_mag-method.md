# Python | Decimal min_mag()方法

> 原文:[https://www . geesforgeks . org/python-decimal-min _ mag-method/](https://www.geeksforgeeks.org/python-decimal-min_mag-method/)

**Decimal # min _ mag():min _ mag()**是一个 Decimal 类方法，它比较两个 Decimal 值并返回最小值 2，忽略它们的符号。

```py
Syntax:  Decimal.min_mag()

Parameter:  Decimal values

Return:  minimum of two, with their sign ignored.

```

**代码# 1:min _ mag()方法示例**

```py
# Python Program explaining 
# min_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.min_mag() method
print ("\n\nDecimal a with min_mag() method : ", a.min_mag(a))

print ("Decimal a with min_mag() method : ", a.min_mag(b))

print ("Decimal b with min_mag() method : ", b.min_mag(a))
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with min_mag() method :  -1
Decimal a with min_mag() method :  0.142857
Decimal b with min_mag() method :  0.142857

```

**代码# 2:min _ mag()方法示例**

```py
# Python Program explaining 
# min_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.min_mag() method
print ("\n\nDecimal a with min_mag() method : ", a.min_mag(a))

print ("Decimal a with min_mag() method : ", a.min_mag(b))

print ("Decimal b with min_mag() method : ", b.min_mag(a))
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with min_mag() method :  -3.14
Decimal a with min_mag() method :  -3.14
Decimal b with min_mag() method :  -3.14

```