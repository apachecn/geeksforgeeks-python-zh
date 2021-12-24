# Python | Decimal compare _ total _ mag()方法

> 原文:[https://www . geesforgeks . org/python-decimal-compare _ total _ mag-method/](https://www.geeksforgeeks.org/python-decimal-compare_total_mag-method/)

**Decimal # compare _ total _ mag():compare _ total _ mag()**是一种 Decimal 类方法，通过使用两个 Decimal 值的抽象表示而不是它们的值来比较这两个 Decimal 值，但忽略每个操作数的符号。

```
Syntax: 
Decimal.compare_total_mag()

Parameter: 
Decimal values

Return: 
1  - if a > b
-1 - if a < b
0  - if a = b

```

**代码# 1:compare _ total _ mag()方法示例**

```
# Python Program explaining 
# compare_total_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare_total_mag() method
print ("\n\nDecimal a with compare_total_mag() method : ", a.compare_total_mag(a))

print ("Decimal a with compare_total_mag() method : ", a.compare_total_mag(b))

print ("Decimal b with compare_total_mag() method : ", b.compare_total_mag(a))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with compare_total_mag() method :  0
Decimal a with compare_total_mag() method :  1
Decimal b with compare_total_mag() method :  -1

```

**代码# 2:compare _ total _ mag()方法示例**

```
# Python Program explaining 
# compare_total_mag() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare_total_mag() method
print ("\n\nDecimal a with compare_total_mag() method : ", a.compare_total_mag(a))

print ("Decimal a with compare_total_mag() method : ", a.compare_total_mag(b))

print ("Decimal b with compare_total_mag() method : ", b.compare_total_mag(a))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with compare_total_mag() method :  0
Decimal a with compare_total_mag() method :  -1
Decimal b with compare_total_mag() method :  1

```