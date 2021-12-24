# Python | Decimal to _ integral _ exact()方法

> 原文:[https://www . geesforgeks . org/python-decimal-to _ integral _ exact-method/](https://www.geeksforgeeks.org/python-decimal-to_integral_exact-method/)

**Decimal # to _ integral _ exact():to _ integral _ exact()**是一个 Decimal 类方法，返回舍入值。

> **语法:** Decimal.to_integral_exact()
> 
> **参数:**十进制值
> 
> **返回:**取整后的整数值。

**代码# 1:to _ integral _ exact()方法示例**

```
# Python Program explaining 
# to_integral_exact() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(1.898989)

b = Decimal(2.0)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.to_integral_exact() method
print ("\n\nDecimal a with to_integral_exact() method : ", a.to_integral_exact())

print ("Decimal b with to_integral_exact() method : ", b.to_integral_exact())
```

**输出:**

```
Decimal value a :  1.8989890000000000380708797820261679589748382568359375
Decimal value b :  2

Decimal a with to_integral_exact() method :  2
Decimal b with to_integral_exact() method :  2

```

**代码# 2:to _ integral _ exact()方法示例**

```
# Python Program explaining 
# to_integral_exact() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(3.14)

b = Decimal(15)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.to_integral_exact() method
print ("\n\nDecimal a with to_integral_exact() method : ", a.to_integral_exact())

print ("Decimal b with to_integral_exact() method : ", b.to_integral_exact())
```

**输出:**

```
Decimal value a :  3.140000000000000124344978758017532527446746826171875
Decimal value b :  15

Decimal a with to_integral_exact() method :  3
Decimal b with to_integral_exact() method :  15

```