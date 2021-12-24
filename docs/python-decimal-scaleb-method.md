# Python | Decimal scaleb()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-scaleb-method/](https://www.geeksforgeeks.org/python-decimal-scaleb-method/)

**Decimal # scaleb():scaleb()**是一个 Decimal 类方法，在将第二个值与其 exp 相加后返回第一个操作数。

> **语法:** Decimal.scaleb()
> 
> **参数:**十进制值
> 
> **返回:**将第二个值与其 exp 相加后的第一个操作数。

**代码# 1:scaleb()方法示例**

```
# Python Program explaining 
# scaleb() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(1)

b = Decimal(0)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.scaleb() method
print ("\n\nDecimal a with scaleb() method : ", a.scaleb(b))

print ("Decimal b with scaleb() method : ", b.scaleb(b))
```

**输出:**

```
Decimal value a :  1
Decimal value b :  0

Decimal a with scaleb() method :  1
Decimal b with scaleb() method :  0

```

**代码# 2:scaleb()方法示例**

```
# Python Program explaining 
# scaleb() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(3)

b = Decimal(2)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.scaleb() method
print ("\n\nDecimal a with scaleb() method : ", a.scaleb(b))

print ("Decimal b with scaleb() method : ", b.scaleb(b))
```

**输出:**

```
Decimal value a :  3
Decimal value b :  2

Decimal a with scaleb() method :  3E+2
Decimal b with scaleb() method :  2E+2

```