# Python | Decimal is _ 有限()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ limited-method/](https://www.geeksforgeeks.org/python-decimal-is_finite-method/)

**Decimal # is _ 有限():is _ 有限()**是 Decimal 类方法，检查 Decimal 值是否为有限值。

> **语法:**decimal . is _ limited()
> 
> **参数:**十进制值
> 
> **返回:**true–如果十进制值是有限值；否则为假

**代码# 1:is _ 有限()方法示例**

```py
# Python Program explaining 
# is_finite() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('-inf')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_finite() method
print ("\n\nDecimal a with is_finite() method : ", a.is_finite())

print ("Decimal b with is_finite() method : ", b.is_finite())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  -Infinity

Decimal a with is_finite() method :  True
Decimal b with is_finite() method :  False

```

**代码# 2:is _ 有限()方法示例**

```py
# Python Program explaining 
# is_finite() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_finite() method
print ("\n\nDecimal a with is_finite() method : ", a.is_finite())

print ("Decimal b with is_finite() method : ", b.is_finite())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_finite() method :  True
Decimal b with is_finite() method :  True

```