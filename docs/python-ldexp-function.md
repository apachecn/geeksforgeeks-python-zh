# Python | ldexp()函数

> 原文:[https://www.geeksforgeeks.org/python-ldexp-function/](https://www.geeksforgeeks.org/python-ldexp-function/)

**`ldexp()`** 函数是 Python 中的 Standard 数学库函数之一，返回 **x * (2**i)** 。这也叫 Python 的逆`frexp()`函数。

> **语法:** math.ldexp(x，I)
> 
> **参数:**
> **x :** 任意有效数字(+ve 或-ve)
> **i :** 任意有效数字(+ve 或-ve)
> 
> **返回:**返回 x * (2**i)的值。

例如，如果 x = 3，i = 4，那么，Math.ldexp(3，4) = 3*16 = 48。

**代码#1:**

```py
# Python3 code demonstrate ldexp() function

# importing math library
import math 

# ldexp() Function on +ve nd -ve Numbers
print(math.ldexp(9, 3))
print(math.ldexp(-5, 2))

# ldexp() Function on fractional Number
print(math.ldexp(3.5, 2))
print('%.2f' %math.ldexp(-6.8, 3))
```

**输出:**

```py
72.0
-20.0
14.0
-54.40

```

**代码#2:**

```py
# Python3 code demonstrate ldexp() function

# importing math library
import math 

# Tuple Declaration 
tpl = (9, -5, 3.5, -6.8)

# List Declaration 
lst = [13, 4, 8.4, -6.7]

# ldexp() Function on +ve nd -ve Numbers
print(math.ldexp(tpl[0], 3))
print(math.ldexp(tpl[3], 2))

# ldexp() Function on fractional Number
print(math.ldexp(lst[1], 2))
print('%.2f' %math.ldexp(lst[2], 3))
```

**输出:**

```py
72.0
-27.2
16.0
67.20
```

**代码#3:** 如果 X 值或 I 值参数不是数字，ldexp()函数将返回**类型错误**。

```py
# Python3 code demonstrates when error occurs

# importing the math library
import math

# string value taken 
print(math.ldexp('25', 5))
print(math.ldexp(25, '5'))
```

**输出:**

```py
TypeError: a float is required
TypeError: a float is required
```