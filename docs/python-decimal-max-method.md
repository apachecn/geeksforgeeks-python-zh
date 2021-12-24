# Python | Decimal max()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-max-method/](https://www.geeksforgeeks.org/python-decimal-max-method/)

**Decimal#max() : max()** 是一个 Decimal 类方法，它比较两个 Decimal 值并返回最大值 2。

```
Syntax:  Decimal.max()

Parameter:  Decimal values

Return:  the max of two.

```

**代码# 1:max()方法示例**

```
# Python Program explaining 
# max() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.max() method
print ("\n\nDecimal a with max() method : ", a.max(a))

print ("Decimal a with max() method : ", a.max(b))

print ("Decimal b with max() method : ", b.max(a))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with max() method :  -1
Decimal a with max() method :  0.142857
Decimal b with max() method :  0.142857

```

**代码# 2:max()方法示例**

```
# Python Program explaining 
# max() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.max() method
print ("\n\nDecimal a with max() method : ", a.max(a))

print ("Decimal a with max() method : ", a.max(b))

print ("Decimal b with max() method : ", b.max(a))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with max() method :  -3.14
Decimal a with max() method :  3.21E+7
Decimal b with max() method :  3.21E+7

```