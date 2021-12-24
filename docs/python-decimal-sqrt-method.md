# Python | Decimal sqrt()方法

> 原文:[https://www.geeksforgeeks.org/python-decimal-sqrt-method/](https://www.geeksforgeeks.org/python-decimal-sqrt-method/)

**Decimal#sqrt() : sqrt()** 是一个 Decimal 类方法，它将非负数的平方根返回到上下文精度。

> **语法:** Decimal.sqrt()
> 
> **参数:**十进制值
> 
> **返回:**非负数的平方根到上下文精度。

**代码# 1:sqrt()方法示例**

```py
# Python Program explaining 
# sqrt() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(1)

b = Decimal(2)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.sqrt() method
print ("\n\nDecimal a with sqrt() method : ", a.sqrt())

print ("Decimal b with sqrt() method : ", b.sqrt())
```

**输出:**

```py
Decimal value a :  1
Decimal value b :  2

Decimal a with sqrt() method :  1
Decimal b with sqrt() method :  1.414213562373095048801688724

```

**代码# 2:sqrt()方法示例**

```py
# Python Program explaining 
# sqrt() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(300)

b = Decimal(15)

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.sqrt() method
print ("\n\nDecimal a with sqrt() method : ", a.sqrt())

print ("Decimal b with sqrt() method : ", b.sqrt())
```

**输出:**

```py
Decimal value a :  300
Decimal value b :  15

Decimal a with sqrt() method :  17.32050807568877293527446342
Decimal b with sqrt() method :  3.872983346207416885179265400

```