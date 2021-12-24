# Python | Decimal logic _ xor()方法

> 原文:[https://www . geesforgeks . org/python-decimal-logic _ xor-method/](https://www.geeksforgeeks.org/python-decimal-logical_xor-method/)

**Decimal # logic _ xor():logic _ xor()**是一个 Decimal 类方法，返回两个 Decimal 值的数字异或。

> **语法:**decimal . logic _ xor()
> 
> **参数:**十进制值
> 
> **返回:**两位(逻辑)十进制值的数字和。

**代码#1:逻辑异或()方法示例**

```
# Python Program explaining 
# logical_xor() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0')

b = Decimal('1')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_xor() method
print ("\n\nDecimal a with logical_xor() method : ", a.logical_xor(b))

print ("Decimal b with logical_xor() method : ", b.logical_xor(b))
```

**输出:**

```
Decimal value a :  0
Decimal value b :  1

Decimal a with logical_xor() method :  1
Decimal b with logical_xor() method :  0

```

**代码#2:逻辑异或()方法示例**

```
# Python Program explaining 
# logical_xor() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('1')

b = Decimal('0')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_xor() method
print ("\n\nDecimal a with logical_xor() method : ", a.logical_xor(a))

print ("Decimal b with logical_xor() method : ", a.logical_xor(b))
```

**输出:**

```
Decimal value a :  1
Decimal value b :  0

Decimal a with logical_xor() method :  0
Decimal b with logical_xor() method :  1

```