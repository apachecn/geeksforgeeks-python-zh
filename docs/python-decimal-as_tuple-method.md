# Python | Decimal as_tuple()方法

> 原文:[https://www . geesforgeks . org/python-decimal-as _ tuple-method/](https://www.geeksforgeeks.org/python-decimal-as_tuple-method/)

**Decimal # as _ tuple():as _ tuple()**是一个 Decimal 类方法，返回 Decimal 值的命名元组表示。

> **语法:** Decimal.as_tuple()
> 
> **参数:**十进制值
> 
> **返回:**元组，值为
> –符号
> –数字
> –指数

**代码# 1:as _ tuple()方法示例**

```
# Python Program explaining 
# as_tuple() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.as_tuple() method
print ("\n\nDecimal a with as_tuple() method : ", a.as_tuple())

print ("Decimal b with as_tuple() method : ", b.as_tuple())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with as_tuple() method :  DecimalTuple(sign=1, digits=(1, ), exponent=0)
Decimal b with as_tuple() method :  DecimalTuple(sign=0, digits=(1, 4, 2, 8, 5, 7), exponent=-6)

```

**代码# 2:as _ tuple()方法示例**

```
# Python Program explaining 
# as_tuple() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.as_tuple() method
print ("\n\nDecimal a with as_tuple() method : ", a.as_tuple())

print ("Decimal b with as_tuple() method : ", b.as_tuple())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with as_tuple() method :  DecimalTuple(sign=1, digits=(3, 1, 4), exponent=-2)
Decimal b with as_tuple() method :  DecimalTuple(sign=0, digits=(3, 2, 1), exponent=5)

```