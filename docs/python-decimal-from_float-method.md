# Python | Decimal from_float()方法

> 原文:[https://www . geesforgeks . org/python-decimal-from _ float-method/](https://www.geeksforgeeks.org/python-decimal-from_float-method/)

**Decimal # from _ float():from _ float()**是一个 Decimal 类方法，它将浮点数精确地转换为十进制数。

> **语法:**十进制. from_float()
> 
> **参数:**十进制值
> 
> **Return:** 将浮点数准确地转换为十进制数。

**代码# 1:from _ float()方法示例**

```
# Python Program explaining 
# from_float() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.from_float() method
print ("\n\nDecimal a with from_float() method : ", a.from_float(0.1))

print ("Decimal b with from_float() method : ", b.from_float(float('nan')))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with from_float() method :  0.1000000000000000055511151231257827021181583404541015625
Decimal b with from_float() method :  NaN

```

**代码# 2:from _ float()方法示例**

```
# Python Program explaining 
# from_float() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.from_float() method
print ("\n\nDecimal a with from_float() method : ", a.from_float(0.02))

print ("Decimal b with from_float() method : ", b.from_float(float('-inf')))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with from_float() method :  0.0200000000000000004163336342344337026588618755340576171875
Decimal b with from_float() method :  -Infinity

```