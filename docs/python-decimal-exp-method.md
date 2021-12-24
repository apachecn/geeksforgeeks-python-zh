# Python | Decimal exp()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-exp-method/](https://www.geeksforgeeks.org/python-decimal-exp-method/)

**Decimal#exp() : exp()** 是一个 Decimal 类方法，它返回给定数字的(自然)指数函数 e**x 的值

> **语法:** Decimal.exp()
> 
> **参数:**十进制值
> 
> **返回:**给定数目的(自然)指数函数 e**x 的值

**代码# 1:exp()方法示例**

```
# Python Program explaining 
# exp() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.exp() method
print ("\n\nDecimal a with exp() method : ", a.exp())

print ("Decimal b with exp() method : ", b.exp())
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with exp() method :  0.3678794411714423215955237702
Decimal b with exp() method :  1.153564830100120253802476512

```

**代码# 2:exp()方法示例**

```
# Python Program explaining 
# exp() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('7.555')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.exp() method
print ("\n\nDecimal a with exp() method : ", a.exp())

print ("Decimal b with exp() method : ", b.exp())
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  7.555

Decimal a with exp() method :  0.04328279790196590079772976615
Decimal b with exp() method :  1910.270243928773816178935745

```