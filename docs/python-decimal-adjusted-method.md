# Python |十进制调整()方法

> 原文:[https://www . geesforgeks . org/python-十进制-调整-方法/](https://www.geeksforgeeks.org/python-decimal-adjusted-method/)

**Decimal # adjusted():adjusted()**是一个 Decimal 类方法，它在移出系数最右边的数字直到只剩下前导数字后返回调整后的指数

> **语法:**十进制.已调整()
> 
> **参数:**十进制值
> 
> **返回:**移出系数最右边的数字直到只剩下前导数字后的调整指数。

**代码#1:调整()方法示例**

```py
# Python Program explaining 
# adjusted() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.adjusted() method
print ("\n\nDecimal a with adjusted() method : ", a.adjusted())

print ("Decimal b with adjusted() method : ", b.adjusted())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with adjusted() method :  0
Decimal b with adjusted() method :  -1

```

**代码#2:调整()方法示例**

```py
# Python Program explaining 
# adjusted() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.adjusted() method
print ("\n\nDecimal a with adjusted() method : ", a.adjusted())

print ("Decimal b with adjusted() method : ", b.adjusted())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with adjusted() method :  0
Decimal b with adjusted() method :  7

```