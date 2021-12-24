# Python | Decimal is_infinite()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ infinite-method/](https://www.geeksforgeeks.org/python-decimal-is_infinite-method/)

**Decimal # is _ infinite():is _ infinite()**是一个 Decimal 类方法，检查 Decimal 值是否为无穷大值。

> **语法:** Decimal.is_infinite()
> 
> **参数:**十进制值
> 
> **返回:**true–如果十进制值为无穷大值；否则为假

**代码# 1:is _ infinite()方法示例**

```py
# Python Program explaining 
# is_infinite() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('-inf')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_infinite() method
print ("\n\nDecimal a with is_infinite() method : ", a.is_infinite())

print ("Decimal b with is_infinite() method : ", b.is_infinite())
```

**输出:**

```py
Decimal value a :  -1
Decimal value b :  -Infinity

Decimal a with is_infinite() method :  False
Decimal b with is_infinite() method :  True

```

**代码# 2:is _ infinite()方法示例**

```py
# Python Program explaining 
# is_infinite() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_infinite() method
print ("\n\nDecimal a with is_infinite() method : ", a.is_infinite())

print ("Decimal b with is_infinite() method : ", b.is_infinite())
```

**输出:**

```py
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_infinite() method :  False
Decimal b with is_infinite() method :  False

```