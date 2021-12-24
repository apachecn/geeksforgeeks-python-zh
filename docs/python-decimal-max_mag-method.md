# Python | Decimal max_mag()方法

> 原文:[https://www . geesforgeks . org/python-decimal-max _ mag-method/](https://www.geeksforgeeks.org/python-decimal-max_mag-method/)

**Decimal # max _ mag():max _ mag()**是一个 Decimal 类方法，它比较两个 Decimal 值并返回两个的最大值，忽略它们的符号。

```
Syntax:  Decimal.max_mag()

Parameter:  Decimal values

Return:  the max_mag of two, with their sign ignored.

```

**代码# 1:max _ mag()方法示例**

```
# Python Program explaining 
# max_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.max_mag() method
print ("\n\nDecimal a with max_mag() method : ", a.max_mag(a))

print ("Decimal a with max_mag() method : ", a.max_mag(b))

print ("Decimal b with max_mag() method : ", b.max_mag(a))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with max_mag() method :  -1
Decimal a with max_mag() method :  -1
Decimal b with max_mag() method :  -1

```

**代码# 2:max _ mag()方法示例**

```
# Python Program explaining 
# max_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.max_mag() method
print ("\n\nDecimal a with max_mag() method : ", a.max_mag(a))

print ("Decimal a with max_mag() method : ", a.max_mag(b))

print ("Decimal b with max_mag() method : ", b.max_mag(a))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with max_mag() method :  -3.14
Decimal a with max_mag() method :  3.21E+7
Decimal b with max_mag() method :  3.21E+7

```