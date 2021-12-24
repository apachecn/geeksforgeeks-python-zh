# Python | Decimal is_subnormal()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ subnormal-method/](https://www.geeksforgeeks.org/python-decimal-is_subnormal-method/)

**Decimal # is _ subnormal():is _ subnormal()**是 Decimal 类方法，检查 Decimal 值是否低于正常值。

```py
Syntax: 
Decimal.is_subnormal()

Parameter: 
Decimal values

Return: 
true - if the Decimal value is subnormal
otherwise false

```

**代码# 1:is _ subnormal()方法示例**

```py
# Python Program explaining 
# is_subnormal() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('-inf')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_subnormal() method
print ("\n\nDecimal a with is_subnormal() method : ", a.is_subnormal())

print ("Decimal b with is_subnormal() method : ", b.is_subnormal())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  -Infinity

Decimal a with is_subnormal() method :  False
Decimal b with is_subnormal() method :  False

```

**代码# 2:is _ subnormal()方法示例**

```py
# Python Program explaining 
# is_subnormal() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_subnormal() method
print ("\n\nDecimal a with is_subnormal() method : ", a.is_subnormal())

print ("Decimal b with is_subnormal() method : ", b.is_subnormal())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_subnormal() method :  False
Decimal b with is_subnormal() method :  False

```