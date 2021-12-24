# Python |十进制典范()方法

> 原文:[https://www . geesforgeks . org/python-decimal-canonical-method/](https://www.geeksforgeeks.org/python-decimal-canonical-method/)

**Decimal # canonical():canonical()**是一个 Decimal 类方法，返回 Decimal 值的规范编码。

> **语法:**十进制.规范()
> 
> **参数:**十进制值
> 
> **返回:**十进制值的规范编码。

**代码#1:规范()方法示例**

```
# Python Program explaining 
# canonical() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.canonical() method
print ("\n\nDecimal a with canonical() method : ", a.canonical())

print ("Decimal b with canonical() method : ", b.canonical())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with canonical() method :  -1
Decimal b with canonical() method :  0.142857

```

**代码#2:规范()方法示例**

```
# Python Program explaining 
# canonical() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.canonical() method
print ("\n\nDecimal a with canonical() method : ", a.canonical())

print ("Decimal b with canonical() method : ", b.canonical())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with canonical() method :  -3.14
Decimal b with canonical() method :  3.21E+7

```