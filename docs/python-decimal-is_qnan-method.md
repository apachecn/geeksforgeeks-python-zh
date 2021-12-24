# Python | Decimal is_qnan()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ qnan-method/](https://www.geeksforgeeks.org/python-decimal-is_qnan-method/)

**Decimal # is _ qnan():is _ qnan()**是 Decimal 类方法，检查 Decimal 值是否是相当 nan 的值。

> **语法:** Decimal.is_qnan()
> 
> **参数:**十进制值
> 
> **返回:**true–如果十进制值相当于 NaN 值；否则为假

**代码# 1:is _ qnan()方法示例**

```
# Python Program explaining 
# is_qnan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('nan')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_qnan() method
print ("\n\nDecimal a with is_qnan() method : ", a.is_qnan())

print ("Decimal b with is_qnan() method : ", b.is_qnan())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  NaN

Decimal a with is_qnan() method :  False
Decimal b with is_qnan() method :  True

```

**代码# 2:is _ qnan()方法示例**

```
# Python Program explaining 
# is_qnan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e+5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_qnan() method
print ("\n\nDecimal a with is_qnan() method : ", a.is_qnan())

print ("Decimal b with is_qnan() method : ", b.is_qnan())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_qnan() method :  False
Decimal b with is_qnan() method :  False

```