# Python | Decimal same_quantum()方法

> 原文:[https://www . geesforgeks . org/python-decimal-same _ quantum-method/](https://www.geeksforgeeks.org/python-decimal-same_quantum-method/)

**Decimal # same _ quantum():same _ quantum()**是 Decimal 类方法，检查两个操作数是否具有相同的指数。

> **语法:** Decimal.same_quantum()
> 
> **参数:**十进制值
> 
> **返回:**true–如果两个操作数的指数相同；否则为假

**代码# 1:same _ quantum()方法示例**

```
# Python Program explaining 
# same_quantum() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.same_quantum() method
print ("\n\nDecimal a with same_quantum() method : ", a.same_quantum(b))

print ("Decimal b with same_quantum() method : ", b.same_quantum(b))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with same_quantum() method :  False
Decimal b with same_quantum() method :  True

```

**代码# 2:same _ quantum()方法示例**

```
# Python Program explaining 
# same_quantum() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.same_quantum() method
print ("\n\nDecimal a with same_quantum() method : ", a.same_quantum(b))

print ("Decimal b with same_quantum() method : ", b.same_quantum(b))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with same_quantum() method :  False
Decimal b with same_quantum() method :  True

```