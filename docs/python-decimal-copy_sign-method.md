# Python | Decimal copy_sign()方法

> 原文:[https://www . geesforgeks . org/python-decimal-copy _ sign-method/](https://www.geeksforgeeks.org/python-decimal-copy_sign-method/)

**Decimal # copy _ sign():copy _ sign()**是一个 Decimal 类方法，返回第一个 Decimal 值的副本，符号设置为与第二个 Decimal 值的符号相同。

```
Syntax: 
Decimal.copy_sign()

Parameter: 
Decimal values

Return: 
the copy of the first Decimal value with the sign set
to be the same as the sign of the second Decimal value.

```

**代码# 1:copy _ sign()方法示例**

```
# Python Program explaining 
# copy_sign() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_sign() method
print ("\n\nDecimal a with copy_sign() method : ", a.copy_sign(a))

print ("Decimal a with copy_sign() method : ", a.copy_sign(b))

print ("Decimal b with copy_sign() method : ", b.copy_sign(a))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with copy_sign() method :  -1
Decimal a with copy_sign() method :  1
Decimal b with copy_sign() method :  -0.142857

```

**代码# 2:copy _ sign()方法示例**

```
# Python Program explaining 
# copy_sign() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_sign() method
print ("\n\nDecimal a with copy_sign() method : ", a.copy_sign(a))

print ("Decimal a with copy_sign() method : ", a.copy_sign(b))

print ("Decimal b with copy_sign() method : ", b.copy_sign(a))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with copy_sign() method :  -3.14
Decimal a with copy_sign() method :  3.14
Decimal b with copy_sign() method :  -3.21E+7

```