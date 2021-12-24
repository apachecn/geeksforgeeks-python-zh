# Python | Decimal next _ 朝()方法

> 原文:[https://www . geesforgeks . org/python-decimal-next _ 朝向-method/](https://www.geeksforgeeks.org/python-decimal-next_toward-method/)

**Decimal # next _ 朝向():next _ 朝向()**是一个 Decimal 类方法，它返回在朝向第二个小数值的方向上最接近第一个小数值的数字。

> **语法:**decimal . next _ 朝()
> 
> **参数:**十进制值
> 
> **返回:**向第二个小数值方向最接近第一个小数值的数字。

**代码# 1:next _ 朝向()方法示例**

```
# Python Program explaining 
# next_toward() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal(-1)

b = Decimal('0.142857')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.next_toward() method
print ("\n\nDecimal a with next_toward() method : ", a.next_toward(b))

print ("Decimal b with next_toward() method : ", b.next_toward(b))
```

**输出:**

```
Decimal value a :  -1
Decimal value b :  0.142857

Decimal a with next_toward() method :  -0.9999999999999999999999999999
Decimal b with next_toward() method :  0.142857

```

**代码# 2:next _ 朝向()方法示例**

```
# Python Program explaining 
# next_toward() method

# loading decimal library
from decimal import *

# Initializing a decimal value
a = Decimal('-3.14')

b = Decimal('321e + 5')

# printing Decimal values
print ("Decimal value a : ", a)
print ("Decimal value b : ", b)

# Using Decimal.next_toward() method
print ("\n\nDecimal a with next_toward() method : ", a.next_toward(b))

print ("Decimal b with next_toward() method : ", b.next_toward(b))
```

**输出:**

```
Decimal value a :  -3.14
Decimal value b :  3.21E+7

Decimal a with next_toward() method :  -3.139999999999999999999999999
Decimal b with next_toward() method :  3.21E+7

```