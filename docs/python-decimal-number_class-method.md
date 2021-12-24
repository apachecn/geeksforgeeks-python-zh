# Python | Decimal number_class()方法

> 原文:[https://www . geesforgeks . org/python-decimal-number _ class-method/](https://www.geeksforgeeks.org/python-decimal-number_class-method/)

**Decimal # number _ class():number _ class()**是一个 Decimal 类方法，返回 Decimal 值的类的指示。

```py
Syntax:  Decimal.number_class()

Parameter:  Decimal values

Return:  indication of the class of Decimal value. 

```

**代码# 1:number _ class()方法示例**

```py
# Python Program explaining 
# number_class() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.number_class() method
print ("\n\nDecimal a with number_class() method : ", a.number_class())

print ("Decimal b with number_class() method : ", b.number_class())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with number_class() method :  -Normal
Decimal b with number_class() method :  +Normal

```

**代码# 2:number _ class()方法示例**

```py
# Python Program explaining 
# number_class() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.number_class() method
print ("\n\nDecimal a with number_class() method : ", a.number_class())

print ("Decimal b with number_class() method : ", b.number_class())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with number_class() method :  -Normal
Decimal b with number_class() method :  +Normal

```