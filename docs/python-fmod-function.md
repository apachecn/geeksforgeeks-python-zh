# Python | fmod()函数

> 原文:[https://www.geeksforgeeks.org/python-fmod-function/](https://www.geeksforgeeks.org/python-fmod-function/)

**`fmod()`** 函数是 Python 中的标准数学库函数之一，用于计算指定给定参数的 Module。

> **语法:** math.fmod( x，y)
> 
> **参数:**
> x 任意有效数字(正数或负数)。
> y 任意有效数字(正数或负数)。
> 
> **返回:**计算给定参数 x 和 y 的模后，返回一个浮点数值。

**示例#1:**

```py
# Python3 program to demonstrate fmod() function

import math

# Tuple Declaration
Tup = (15, 22, -2, -40 )

# List Declaration
Lis = [-89, 38, -39, 16] 

# modulus of +ve integer number
print(math.fmod(4, 5))
print(math.fmod(43.50, 4.5))

# modulus of -ve integer number
print(math.fmod(-17, 5))
print('%.2f' %math.fmod(-10, 4.78))

# modulus of tuple item
print("\nModulus of tuple items:")
print(math.fmod(Tup[2], 5))
print(math.fmod(Tup[2], -6))

# modulus of list item
print("\nModulus of list items:")
print(math.fmod(Lis[3], 4))
print(math.fmod(Lis[0], -15))
```

**输出:**

```py
4.0
3.0
-2.0
-0.44

Modulus of tuple items:
-2.0
-2.0

Modulus of list items:
0.0
-14.0

```

**示例#2:** 值错误和类型错误

*   如果 x 和 y 参数都为零，fmod()函数将返回输出为**值错误**。
*   如果 y 参数(第二个参数)为零，fmod()函数将返回输出为**值错误**。
*   如果 x 值或 y 值不是数字，fmod()函数将返回**类型错误**。

```py
# Python3 program to demonstrate 
# errors in fmod() function

import math

# will give ValueError
print(math.fmod(0, 0))
print(math.fmod(2, 0))

# it will give TypeError
print(math.fmod('2', 3))
```

**输出:**

```py
ValueError: math domain error
ValueError: math domain error
TypeError: a float is required

```