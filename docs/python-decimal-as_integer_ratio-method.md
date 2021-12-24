# Python | Decimal as _ integer _ ratio()方法

> 原文:[https://www . geesforgeks . org/python-decimal-as _ integer _ ratio-method/](https://www.geeksforgeeks.org/python-decimal-as_integer_ratio-method/)

**Decimal # as _ integer _ ratio():as _ integer _ ratio()**是一个 Decimal 类方法，它在移出系数最右边的数字直到只剩下前导数字时返回指数:作为一对(n，d)

> **语法:** Decimal.as_integer_ratio()
> 
> **参数:**十进制值
> 
> **返回:**移出系数最右边的数字直到只剩下前导数字后的指数:成对(n，d)

**代码# 1:as _ integer _ ratio()方法示例**

```
# Python Program explaining 
# as_integer_ratio() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.as_integer_ratio() method
print ("\n\nDecimal a with as_integer_ratio() method : ", a.as_integer_ratio())

print ("Decimal b with as_integer_ratio() method : ", b.as_integer_ratio())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with as_integer_ratio() method :  (-1, 1)
Decimal b with as_integer_ratio() method :  (142857, 1000000)

```

**代码# 2:as _ integer _ ratio()方法示例**

```
# Python Program explaining 
# as_integer_ratio() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.as_integer_ratio() method
print ("\n\nDecimal a with as_integer_ratio() method : ", a.as_integer_ratio())

print ("Decimal b with as_integer_ratio() method : ", b.as_integer_ratio())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with as_integer_ratio() method :  (-157, 50)
Decimal b with as_integer_ratio() method :  (32100000, 1)

```