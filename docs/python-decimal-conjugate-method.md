# Python | Decimal 共轭()方法

> 原文:[https://www . geesforgeks . org/python-十进制-共轭-方法/](https://www.geeksforgeeks.org/python-decimal-conjugate-method/)

**Decimal #共轭() :共轭()**是一个返回自身的 Decimal 类方法，这个方法只是为了遵守 Decimal 规范

```py
Syntax: 
Decimal.conjugate()

Parameter: 
Decimal values

Return: 
the self Decimal value

```

**代码#1:共轭()方法示例**

```py
# Python Program explaining 
# conjugate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.conjugate() method
print ("\n\nDecimal a with conjugate() method : ", a.conjugate())

print ("Decimal b with conjugate() method : ", b.conjugate())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with conjugate() method :  -1
Decimal b with conjugate() method :  0.142857

```

**代码#2:共轭()方法示例**

```py
# Python Program explaining 
# conjugate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.conjugate() method
print ("\n\nDecimal a with conjugate() method : ", a.conjugate())

print ("Decimal b with conjugate() method : ", b.conjugate())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with conjugate() method :  -3.14
Decimal b with conjugate() method :  3.21E+7

```