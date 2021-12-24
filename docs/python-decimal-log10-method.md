# Python | Decimal log10()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-log10-method/](https://www.geeksforgeeks.org/python-decimal-log10-method/)

**Decimal#log10() : log10()** 是一个 Decimal 类方法，返回 Decimal 值的以十为底的对数。

> **语法:** Decimal.log10()
> 
> **参数:**十进制值
> 
> **返回:**十进制值的以十为底的对数。

**代码# 1:log 10()方法示例**

```
# Python Program explaining 
# log10() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('.9932')

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.log10() method
print ("\n\nDecimal a with log10() method : ", a.log10())

print ("Decimal b with log10() method : ", b.log10())
```

**输出:**

```
Decimal value a :  0.9932
Decimal value b :  0.142857

Decimal a with log10() method :  -0.002963289117473302730973454338
Decimal b with log10() method :  -0.8450984743089558813497604715

```

**代码# 2:log 10()方法示例**

```
# Python Program explaining 
# log10() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.log10() method
print ("\n\nDecimal a with log10() method : ", a.log10())

print ("Decimal b with log10() method : ", b.log10())
```

**输出:**

```
Decimal value a :  3.14
Decimal value b :  3.21E+7

Decimal a with log10() method :  0.4969296480732149319752200246
Decimal b with log10() method :  7.506505032404872078129569143

```