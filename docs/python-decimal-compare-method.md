# Python | Decimal compare()方法

> 原文:[https://www . geesforgeks . org/python-decimal-compare-method/](https://www.geeksforgeeks.org/python-decimal-compare-method/)

**Decimal # compare():compare()**是比较两个 Decimal 值的 Decimal 类方法。

> **语法:**十进制.比较()
> 
> **参数:**十进制值
> 
> **返回:**
> 1–如果 a>b
> -1–如果 a<b
> 0–如果 a = b

**代码# 1:compare()方法示例**

```
# Python Program explaining 
# compare() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare() method
print ("\n\nDecimal a with compare() method : ", a.compare(a))

print ("Decimal a with compare() method : ", a.compare(b))

print ("Decimal b with compare() method : ", b.compare(a))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with compare() method :  0
Decimal a with compare() method :  -1
Decimal b with compare() method :  1

```

**代码# 2:compare()方法示例**

```
# Python Program explaining 
# compare() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.compare() method
print ("\n\nDecimal a with compare() method : ", a.compare(a))

print ("Decimal a with compare() method : ", a.compare(b))

print ("Decimal b with compare() method : ", b.compare(a))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with compare() method :  0
Decimal a with compare() method :  -1
Decimal b with compare() method :  1

```