# Python | Decimal is_normal()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ normal-method/](https://www.geeksforgeeks.org/python-decimal-is_normal-method/)

**Decimal # is _ normal():is _ normal()**是 Decimal 类方法，检查 Decimal 值是否为正常的有限数。

> **语法:** Decimal.is_normal()
> 
> **参数:**十进制值
> 
> **返回:**true–如果十进制值是正常的有限数字；否则为假

**代码# 1:is _ normal()方法示例**

```
# Python Program explaining 
# is_normal() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('-inf')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_normal() method
print ("\n\nDecimal a with is_normal() method : ", a.is_normal())

print ("Decimal b with is_normal() method : ", b.is_normal())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  -Infinity

Decimal a with is_normal() method :  True
Decimal b with is_normal() method :  False

```

**代码# 2:is _ normal()方法示例**

```
# Python Program explaining 
# is_normal() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_normal() method
print ("\n\nDecimal a with is_normal() method : ", a.is_normal())

print ("Decimal b with is_normal() method : ", b.is_normal())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_normal() method :  True
Decimal b with is_normal() method :  True

```