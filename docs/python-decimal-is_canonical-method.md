# Python | Decimal is_canonical()方法

> 原文:[https://www . geesforgeks . org/python-decimal-is _ canonical-method/](https://www.geeksforgeeks.org/python-decimal-is_canonical-method/)

**Decimal # is _ canonical():is _ canonical()**是一个 Decimal 类方法，用于检查 Decimal 值是否规范。

> **语法:** Decimal.is_canonical()
> 
> **参数:**十进制值
> 
> **返回:**true–如果十进制值是规范的；否则为假

**代码# 1:is _ canonical()方法示例**

```
# Python Program explaining 
# is_canonical() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_canonical() method
print ("\n\nDecimal a with is_canonical() method : ", a.is_canonical())

print ("Decimal b with is_canonical() method : ", b.is_canonical())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with is_canonical() method :  True
Decimal b with is_canonical() method :  True

```

**代码# 2:is _ canonical()方法示例**

```
# Python Program explaining 
# is_canonical() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.is_canonical() method
print ("\n\nDecimal a with is_canonical() method : ", a.is_canonical())

print ("Decimal b with is_canonical() method : ", b.is_canonical())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with is_canonical() method :  True
Decimal b with is_canonical() method :  True

```