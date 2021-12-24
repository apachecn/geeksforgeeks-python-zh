# Python | frexp()函数

> 原文:[https://www.geeksforgeeks.org/python-frexp-function/](https://www.geeksforgeeks.org/python-frexp-function/)

**`frexp()`** 函数是 Python 中的标准数学库函数之一。

它将尾数和指数作为给定值 x 的一对(m，e)返回，其中尾数 **m** 是浮点数， **e** 指数是整数值。 **m** 是一个浮点数 **e** 是一个整数使得 **x == m * 2**e** 精确。

如果 x 为零，则返回(0.0，0)，否则返回 0.5 <= abs(m) < 1。这用于以可移植的方式“挑选”一个浮动的内部表示。

> **语法:** math.frexp( x)
> 
> **参数:**任意有效数字(正数或负数)。
> 
> **返回:**返回给定数字 x 的尾数和指数对(m，e)值。
> 
> **异常:**如果 **x** 不是数字，函数将返回 TypeError。

**代码#1:**

```
# Python3 code demonstrate frexp() function

# importing math library
import math

# calculating mantissa and
# exponent of given integer
print(math.frexp(3))
print(math.frexp(15.7))
print(math.frexp(-15))
```

**输出:**

```
(0.75, 2)
(0.98125, 4)
(-0.9375, 4)

```

**代码#2:**

```
# Python3 code demonstrate frexp() function

# importing math library
import math

# creating a list
lst = [15, 13.76, 17.5, 21]

# creating a tuple
tpl = (-15.85, -41.24, -11.2, 54)

# calculating mantissa and exponent
# of 1st, 3rd elements in list 
print(math.frexp(lst[0]))
print(math.frexp(lst[2]))

# calculating mantissa and exponent
# of 2nd, 3rd and 4th elements in tuple 
print(math.frexp(tpl[1]))
print(math.frexp(tpl[2]))
print(math.frexp(tpl[3]))
```

输出:

```
(0.9375, 4)
(0.546875, 5)
(-0.644375, 6)
(-0.7, 4)
(0.84375, 6)
```

**代码#3:** 如果 x 参数不是数字，`frexp()`函数将返回一个**类型错误**。

```
# Python3 code demonstrates when error occurs
import math

print(math.frexp('25')) 
```

**输出:**

```
TypeError: a float is required
```