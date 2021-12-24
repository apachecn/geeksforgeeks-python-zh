# Python | Decimal copy_abs()方法

> 原文:[https://www . geesforgeks . org/python-decimal-copy _ ABS-method/](https://www.geeksforgeeks.org/python-decimal-copy_abs-method/)

**Decimal # copy _ ABS():copy _ ABS()**是一个 Decimal 类方法，返回 Decimal 的绝对值。

> **语法:** Decimal.copy_abs()
> 
> **参数:**十进制值
> 
> **返回:**绝对十进制值

**代码# 1:copy _ ABS()方法示例**

```
# Python Program explaining 
# copy_abs() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_abs() method
print ("\n\nDecimal a with copy_abs() method : ", a.copy_abs())

print ("Decimal b with copy_abs() method : ", b.copy_abs())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with copy_abs() method :  1
Decimal b with copy_abs() method :  0.142857

```

**代码# 2:copy _ ABS()方法示例**

```
# Python Program explaining 
# copy_abs() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.copy_abs() method
print ("\n\nDecimal a with copy_abs() method : ", a.copy_abs())

print ("Decimal b with copy_abs() method : ", b.copy_abs())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with copy_abs() method :  3.14
Decimal b with copy_abs() method :  3.21E+7

```