# Python | Decimal is_snan()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ snan-method/](https://www.geeksforgeeks.org/python-decimal-is_snan-method/)

**Decimal # is _ snan():is _ snan()**是一种 Decimal 类方法，用于检查 Decimal 值是否是信号 nan

> **语法:** Decimal.is_snan()
> 
> **参数:**十进制值
> 
> **返回:**true–如果十进制值是信号 NaN 否则为假

**代码# 1:is _ snan()方法示例**

```
# Python Program explaining 
# is_snan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('nan')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_snan() method
print ("\n\nDecimal a with is_snan() method : ", a.is_snan())

print ("Decimal b with is_snan() method : ", b.is_snan())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  -NaN

Decimal a with is_snan() method :  False
Decimal b with is_snan() method :  False

```

**代码# 2:is _ snan()方法示例**

```
# Python Program explaining 
# is_snan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_snan() method
print ("\n\nDecimal a with is_snan() method : ", a.is_snan())

print ("Decimal b with is_snan() method : ", b.is_snan())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_snan() method :  False
Decimal b with is_snan() method :  False

```