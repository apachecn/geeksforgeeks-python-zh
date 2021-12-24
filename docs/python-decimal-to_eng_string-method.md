# Python | Decimal to_eng_string()方法

> 原文:[https://www . geesforgeks . org/python-decimal-to _ eng _ string-method/](https://www.geeksforgeeks.org/python-decimal-to_eng_string-method/)

**Decimal # to _ eng _ string():to _ eng _ string()**是一个 Decimal 类方法，它转换为字符串，如果需要指数，则使用工程符号。

> **语法:** Decimal.to_eng_string()
> 
> **参数:**十进制值
> 
> **返回:**转换为字符串

**代码# 1:to _ eng _ string()方法示例**

```py
# Python Program explaining 
# to_eng_string() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(1.898989)

b = Decimal(2.0)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.to_eng_string() method
print ("\n\nDecimal a with to_eng_string() method : ", a.to_eng_string())

print ("Decimal b with to_eng_string() method : ", b.to_eng_string())
```

**输出:**

```py
Decimal value a :  1.8989890000000000380708797820261679589748382568359375
Decimal value b :  2

Decimal a with to_eng_string() method :  1.8989890000000000380708797820261679589748382568359375
Decimal b with to_eng_string() method :  2

```

**代码# 2:to _ eng _ string()方法示例**

```py
# Python Program explaining 
# to_eng_string() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(3.14)

b = Decimal(15)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.to_eng_string() method
print ("\n\nDecimal a with to_eng_string() method : ", a.to_eng_string())

print ("Decimal b with to_eng_string() method : ", b.to_eng_string())
```

**输出:**

```py
Decimal value a :  3.140000000000000124344978758017532527446746826171875
Decimal value b :  15

Decimal a with to_eng_string() method :  3.140000000000000124344978758017532527446746826171875
Decimal b with to_eng_string() method :  15

```