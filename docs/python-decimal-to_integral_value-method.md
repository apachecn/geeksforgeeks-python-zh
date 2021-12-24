# Python | Decimal to _ integral _ value()方法

> 原文:[https://www . geesforgeks . org/python-decimal-to _ integral _ value-method/](https://www.geeksforgeeks.org/python-decimal-to_integral_value-method/)

**十进制# to _ integral _ value():to _ integral _ value()**是一种十进制类方法，它返回最近的整数，而不发出不精确或舍入的信号。

> **语法:** Decimal.to_integral_value()
> 
> **参数:**十进制值
> 
> **返回:**最近的整数，不发送不精确或舍入信号。

**代码# 1:to _ integral _ value()方法示例**

```py
# Python Program explaining 
# to_integral_value() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(1.898989)

b = Decimal(2.0)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.to_integral_value() method
print ("\n\nDecimal a with to_integral_value() method : ", a.to_integral_value())

print ("Decimal b with to_integral_value() method : ", b.to_integral_value())
```

**输出:**

```py
Decimal value a :  1.8989890000000000380708797820261679589748382568359375
Decimal value b :  2

Decimal a with to_integral_value() method :  2
Decimal b with to_integral_value() method :  2

```

**代码# 2:to _ integral _ value()方法示例**

```py
# Python Program explaining 
# to_integral_value() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(3.14)

b = Decimal(15)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.to_integral_value() method
print ("\n\nDecimal a with to_integral_value() method : ", a.to_integral_value())

print ("Decimal b with to_integral_value() method : ", b.to_integral_value())
```

**输出:**

```py
Decimal value a :  3.140000000000000124344978758017532527446746826171875
Decimal value b :  15

Decimal a with to_integral_value() method :  3
Decimal b with to_integral_value() method :  15

```