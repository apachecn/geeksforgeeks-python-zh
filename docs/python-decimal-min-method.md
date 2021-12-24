# Python | Decimal min()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-min-method/](https://www.geeksforgeeks.org/python-decimal-min-method/)

**Decimal#min() : min()** 是一个 Decimal 类方法，它比较两个 Decimal 值并返回两者的 min。

```py
Syntax:  Decimal.min()

Parameter:  Decimal values

Return:  the min of two.

```

**代码# 1:min()方法示例**

```py
# Python Program explaining 
# min() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.min() method
print ("\n\nDecimal a with min() method : ", a.min(a))

print ("Decimal a with min() method : ", a.min(b))

print ("Decimal b with min() method : ", b.min(a))
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with min() method :  -1
Decimal a with min() method :  -1
Decimal b with min() method :  -1

```

**代码# 2:min()方法示例**

```py
# Python Program explaining 
# min() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.min() method
print ("\n\nDecimal a with min() method : ", a.min(a))

print ("Decimal a with min() method : ", a.min(b))

print ("Decimal b with min() method : ", b.min(a))
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with min() method :  -3.14
Decimal a with min() method :  -3.14
Decimal b with min() method :  -3.14

```