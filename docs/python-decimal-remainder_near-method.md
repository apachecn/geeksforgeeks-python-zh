# Python | Decimal 余数 _near()方法

> 原文:[https://www . geesforgeks . org/python-decimal-余数 _near-method/](https://www.geeksforgeeks.org/python-decimal-remainder_near-method/)

**Decimal #余数 _near():余数 _near()** 是一个 Decimal 类方法，返回 x–y * n，其中 n 是最接近 x / y 精确值的整数

> **语法:** Decimal .余数 _near()
> 
> **参数:**十进制值
> 
> **返回:**x–y * n，其中 n 是最接近 x / y 精确值的整数

**代码# 1:`remainder_near()`方法示例**

```py
# Python Program explaining 
# remainder_near() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.remainder_near() method
print ("\n\nDecimal a with remainder_near() method : ", a.remainder_near(b))

print ("Decimal b with remainder_near() method : ", b.remainder_near(b))
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with remainder_near() method :  -0.000001
Decimal b with remainder_near() method :  0.000000

```

**代码# 2:`remainder_near()`方法示例**

```py
# Python Program explaining 
# remainder_near() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.remainder_near() method
print ("\n\nDecimal a with remainder_near() method : ", a.remainder_near(b))

print ("Decimal b with remainder_near() method : ", b.remainder_near(b))
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with remainder_near() method :  -3.14
Decimal b with remainder_near() method :  0E+5

```