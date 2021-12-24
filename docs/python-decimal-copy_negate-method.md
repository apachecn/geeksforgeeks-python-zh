# Python | Decimal copy _ negative()方法

> 原文:[https://www . geesforgeks . org/python-decimal-copy _ negative-method/](https://www.geeksforgeeks.org/python-decimal-copy_negate-method/)

**Decimal # copy _ negative():copy _ negative()**是一个 Decimal 类方法，返回 Decimal 值的否定。

> **语法:**decimal . copy _ negative()
> 
> **参数:**十进制值
> 
> **返回:**十进制值的否定

**代码# 1:copy _ negative()方法示例**

```py
# Python Program explaining 
# copy_negate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_negate() method
print ("\n\nDecimal a with copy_negate() method : ", a.copy_negate())

print ("Decimal b with copy_negate() method : ", b.copy_negate())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with copy_negate() method :  1
Decimal b with copy_negate() method :  -0.142857

```

**代码# 2:copy _ negative()方法示例**

```py
# Python Program explaining 
# copy_negate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_negate() method
print ("\n\nDecimal a with copy_negate() method : ", a.copy_negate())

print ("Decimal b with copy_negate() method : ", b.copy_negate())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with copy_negate() method :  3.14
Decimal b with copy_negate() method :  -3.21E+7

```