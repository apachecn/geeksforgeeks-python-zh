# Python | Decimal next_plus()方法

> 原文:[https://www . geesforgeks . org/python-decimal-next _ plus-method/](https://www.geeksforgeeks.org/python-decimal-next_plus-method/)

**Decimal # next _ plus():next _ plus()**是一个 Decimal 类方法，返回大于 Decimal 值的最小可表示数。

> **语法:** Decimal.next_plus()
> 
> **参数:**十进制值
> 
> **返回:**大于十进制值的最小可表示数。

**代码# 1:next _ plus()方法示例**

```
# Python Program explaining 
# next_plus() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.next_plus() method
print ("\n\nDecimal a with next_plus() method : ", a.next_plus())

print ("Decimal a with next_plus() method : ", a.next_plus())

print ("Decimal b with next_plus() method : ", b.next_plus())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with next_plus() method :  -0.9999999999999999999999999999
Decimal a with next_plus() method :  -0.9999999999999999999999999999
Decimal b with next_plus() method :  0.1428570000000000000000000001

```

**代码# 2:next _ plus()方法示例**

```
# Python Program explaining 
# next_plus() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.next_plus() method
print ("\n\nDecimal a with next_plus() method : ", a.next_plus())

print ("Decimal a with next_plus() method : ", a.next_plus())

print ("Decimal b with next_plus() method : ", b.next_plus())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with next_plus() method :  -3.139999999999999999999999999
Decimal a with next_plus() method :  -3.139999999999999999999999999
Decimal b with next_plus() method :  32100000.00000000000000000001

```