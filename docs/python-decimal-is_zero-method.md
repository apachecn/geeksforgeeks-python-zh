# Python | Decimal is_zero()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ zero-method/](https://www.geeksforgeeks.org/python-decimal-is_zero-method/)

**Decimal # is _ zero():is _ zero()**是 Decimal 类方法，检查 Decimal 值是否为零值。

```py
Syntax: 
Decimal.is_zero()

Parameter: 
Decimal values

Return: 
true - if the Decimal value is zero value; otherwise false

```

**代码# 1:is _ zero()方法示例**

```py
# Python Program explaining 
# is_zero() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal(0)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_zero() method
print ("\n\nDecimal a with is_zero() method : ", a.is_zero())

print ("Decimal b with is_zero() method : ", b.is_zero())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0

Decimal a with is_zero() method :  False
Decimal b with is_zero() method :  True

```

**代码# 2:is _ zero()方法示例**

```py
# Python Program explaining 
# is_zero() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-0)

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_zero() method
print ("\n\nDecimal a with is_zero() method : ", a.is_zero())

print ("Decimal b with is_zero() method : ", b.is_zero())
```

**输出:**

```py
Decimal value a :  0
Decimal value b :  3.21E+7

Decimal a with is_zero() method :  True
Decimal b with is_zero() method :  False

```