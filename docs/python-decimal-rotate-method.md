# Python | Decimal rotate()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-rotate-method/](https://www.geeksforgeeks.org/python-decimal-rotate-method/)

**Decimal # rotate():rotate()**是一个 Decimal 类方法，返回 x，y 次的旋转副本

```
Syntax:  Decimal.rotate()

Parameter:  Decimal values

Return:  the rotated copy of x, y times

```

**代码# 1:`rotate()`方法示例**

```
# Python Program explaining 
# rotate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(1)

b = Decimal(2)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.rotate() method
print ("\n\nDecimal a with rotate() method : ", a.rotate(b))

print ("Decimal b with rotate() method : ", b.rotate(b))
```

**输出:**

```
Decimal value a :  1
Decimal value b :  2

Decimal a with rotate() method :  100
Decimal b with rotate() method :  200

```

**代码#2:旋转()方法示例**

```
# Python Program explaining 
# rotate() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(300)

b = Decimal(15)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.rotate() method
print ("\n\nDecimal a with rotate() method : ", a.rotate(b))

print ("Decimal b with rotate() method : ", b.rotate(b))
```

**输出:**

```
Decimal value a :  300
Decimal value b :  15

Decimal a with rotate() method :  300000000000000000
Decimal b with rotate() method :  15000000000000000

```