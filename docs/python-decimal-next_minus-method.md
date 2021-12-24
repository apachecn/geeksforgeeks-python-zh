# Python | Decimal next _ 减()方法

> 原文:[https://www . geesforgeks . org/python-decimal-next _ next-method/](https://www.geeksforgeeks.org/python-decimal-next_minus-method/)

**Decimal # next _ 减():next _ 减()**是一个 Decimal 类方法，返回小于 Decimal 值的最大可表示数。

> **语法:**decimal . next _ 减号()
> 
> **参数:**十进制值
> 
> **返回:**小于十进制值的最大可表示数。

**代码# 1:next _ 减()方法示例**

```py
# Python Program explaining 
# next_minus() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.next_minus() method
print ("\n\nDecimal a with next_minus() method : ", a.next_minus())

print ("Decimal a with next_minus() method : ", a.next_minus())

print ("Decimal b with next_minus() method : ", b.next_minus())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with next_minus() method :  -1.000000000000000000000000001
Decimal a with next_minus() method :  -1.000000000000000000000000001
Decimal b with next_minus() method :  0.1428569999999999999999999999

```

**代码# 2:next _ 减()方法示例**

```py
# Python Program explaining 
# next_minus() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.next_minus() method
print ("\n\nDecimal a with next_minus() method : ", a.next_minus())

print ("Decimal a with next_minus() method : ", a.next_minus())

print ("Decimal b with next_minus() method : ", b.next_minus())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with next_minus() method :  -3.140000000000000000000000001
Decimal a with next_minus() method :  -3.140000000000000000000000001
Decimal b with next_minus() method :  32099999.99999999999999999999

```