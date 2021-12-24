# Python | Decimal is_nan()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-is_nan-method/](https://www.geeksforgeeks.org/python-decimal-is_nan-method/)

**Decimal # is _ nan():is _ NaN()**是 Decimal 类方法，检查 Decimal 值是否为 NaN 值。

> **语法:** Decimal.is_nan()
> 
> **参数:**十进制值
> 
> **返回:**true–如果十进制值为 NaN 值；否则为假

**代码# 1:is _ nan()方法示例**

```py
# Python Program explaining 
# is_nan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('nan')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_nan() method
print ("\n\nDecimal a with is_nan() method : ", a.is_nan())

print ("Decimal b with is_nan() method : ", b.is_nan())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  NaN

Decimal a with is_nan() method :  False
Decimal b with is_nan() method :  True

```

**代码# 2:is _ nan()方法示例**

```py
# Python Program explaining 
# is_nan() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_nan() method
print ("\n\nDecimal a with is_nan() method : ", a.is_nan())

print ("Decimal b with is_nan() method : ", b.is_nan())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_nan() method :  False
Decimal b with is_nan() method :  False

```