# Python | Decimal 逻辑 _and()方法

> 原文:[https://www . geesforgeks . org/python-decimal-logic _ and-method/](https://www.geeksforgeeks.org/python-decimal-logical_and-method/)

**Decimal # logic _ and():logic _ and()**是一个 Decimal 类方法，它返回两个(逻辑)Decimal 值的数字和。

> **语法:**decimal . logic _ and()
> 
> **参数:**十进制值
> 
> **返回:**两位(逻辑)十进制值的数字和。

**代码#1:逻辑 _and()方法示例**

```
# Python Program explaining 
# logical_and() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('0')

b = Decimal('1')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_and() method
print ("\n\nDecimal a with logical_and() method : ", a.logical_and(b))

print ("Decimal b with logical_and() method : ", b.logical_and(b))
```

**输出:**

```
Decimal value a :  0
Decimal value b :  1

Decimal a with logical_and() method :  0
Decimal b with logical_and() method :  1

```

**代码#2:逻辑 _and()方法示例**

```
# Python Program explaining 
# logical_and() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('1')

b = Decimal('0')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.logical_and() method
print ("\n\nDecimal a with logical_and() method : ", a.logical_and(a))

print ("Decimal b with logical_and() method : ", a.logical_and(b))
```

**输出:**

```
Decimal value a :  1
Decimal value b :  0

Decimal a with logical_and() method :  1
Decimal b with logical_and() method :  0

```