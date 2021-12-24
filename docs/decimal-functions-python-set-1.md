# Python 中的十进制函数|集合 1

> 原文:[https://www . geesforgeks . org/decimal-functions-python-set-1/](https://www.geeksforgeeks.org/decimal-functions-python-set-1/)

Python 在其定义中提供了某些方法来使用模块“decimal”执行更快的十进制浮点运算。
**小数上的重要运算**
**1。sqrt()** :-该函数计算十进制数的**平方根**。
**2。exp()** :-该函数返回十进制数的 **e^x(指数)**。

## 计算机编程语言

```py
# Python code to demonstrate the working of
# sqrt() and exp()

# importing "decimal" module to use decimal functions
import decimal

# using exp() to compute the exponent of decimal number
a = decimal.Decimal(4.5).exp()

# using sqrt() to compute the square root of decimal number
b = decimal.Decimal(4.5).sqrt()

# printing the exponent
print ("The exponent of decimal number is : ",end="")
print (a)

# printing the square root
print ("The square root of decimal number is : ",end="")
print (b)
```

输出:

```py
The exponent of decimal number is : 90.01713130052181355011545675
The square root of decimal number is : 2.121320343559642573202533086
```

**3。ln()** :-该函数用于计算小数的**自然对数**。
**4。log10()** :-该函数用于计算十进制数的 **log(基数 10)** 。

## 计算机编程语言

```py
# Python code to demonstrate the working of
# ln() and log10()

# importing "decimal" module to use decimal functions
import decimal

# using ln() to compute the natural log of decimal number
a = decimal.Decimal(4.5).ln()

# using sqrt() to compute the log10 of decimal number
b = decimal.Decimal(4.5).log10()

# printing the natural logarithm
print ("The natural logarithm of decimal number is : ",end="")
print (a)

# printing the log10
print ("The log(base 10) of decimal number is : ",end="")
print (b)
```

输出:

```py
The natural logarithm of decimal number is : 1.504077396776274073373258352
The log(base 10) of decimal number is : 0.6532125137753436793763169118
```

**5。as_tuple()** :-将十进制数作为包含 **3 个参数、符号(0 代表+，1 代表-)、数字和指数值**的元组返回。
**6。fma(a，b)** :-这个“fma”代表**融合乘加**。它根据参数中的数字计算 **(num*a)+b** 。**此功能中不发生(num*a)** 的舍入。
**例:**

```py
decimal.Decimal(5).fma(2,3) --> (5*2)+3 = 13
```

## 计算机编程语言

```py
# Python code to demonstrate the working of
# as_tuple() and fma()

# importing "decimal" module to use decimal functions
import decimal

# using as_tuple() to return decimal number as tuple
a = decimal.Decimal(-4.5).as_tuple()

# using fma() to compute fused multiply and addition
b = decimal.Decimal(5).fma(2,3)

# printing the tuple
print ("The tuple form of decimal number is : ",end="")
print (a)

# printing the fused multiple and addition
print ("The fused multiply and addition of decimal number is : ",end="")
print (b)
```

输出:

```py
The tuple form of decimal number is : DecimalTuple(sign=1, digits=(4, 5), exponent=-1)
The fused multiply and addition of decimal number is : 13
```

**7。compare()** :-此函数用于比较十进制数。**如果第一个十进制参数大于第二个十进制参数，则返回 1；如果第一个十进制参数小于第二个十进制参数，则返回-1；如果两者相等，则返回 0。**T4**8。compare_total_mag()** :-比较十进制数的总幅度。**如果第一个十进制参数大于第二个(忽略符号)，则返回 1，如果第一个十进制参数小于第二个(忽略符号)，则返回-1，如果两者相等(忽略符号)，则返回 0。**

## 计算机编程语言

```py
# Python code to demonstrate the working of
# compare() and compare_total_mag()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(9.53)

# Initializing decimal number
b = decimal.Decimal(-9.56)

# comparing decimal numbers using compare()
print ("The result of comparison using compare() is : ",end="")
print (a.compare(b))

# comparing decimal numbers using compare_total_mag()
print ("The result of comparison using compare_total_mag() is : ",end="")
print (a.compare_total_mag(b))
```

输出:

```py
The result of comparison using compare() is : 1
The result of comparison using compare_total_mag() is : -1
```

**9。copy_abs()** :-该函数打印十进制参数的**绝对值**。
**10。copy _ negative()**:-该函数打印十进制参数的**否定**。
**11。copy_sign()** :-该函数通过从第二个参数复制符号来打印第一个参数**。** 

## 计算机编程语言

```py
# Python code to demonstrate the working of
# copy_abs(),copy_sign() and copy_negate()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(9.53)

# Initializing decimal number
b = decimal.Decimal(-9.56)

# printing absolute value using copy_abs()
print ("The absolute value using copy_abs() is : ",end="")
print (b.copy_abs())

# printing negated value using copy_negate()
print ("The negated value using copy_negate() is : ",end="")
print (b.copy_negate())

# printing sign effected value using copy_sign()
print ("The sign effected value using copy_sign() is : ",end="")
print (a.copy_sign(b))
```

输出:

```py
The absolute value using copy_abs() is : 9.5600000000000004973799150320701301097869873046875
The negated value using copy_negate() is : 9.5600000000000004973799150320701301097869873046875
The sign effected value using copy_sign() is : -9.5299999999999993605115378159098327159881591796875
```

**12 时。max()** :-该函数计算两个十进制数的**最大值**。
**13。min()** :-该函数计算两个十进制数的**最小值**。

## 计算机编程语言

```py
# Python code to demonstrate the working of
# min() and max()

# importing "decimal" module to use decimal functions
import decimal

# Initializing decimal number
a = decimal.Decimal(9.53)

# Initializing decimal number
b = decimal.Decimal(7.43)

# printing minimum of both values
print ("The minimum of two numbers is : ",end="")
print (a.min(b))

# printing maximum of both values
print ("The maximum of two numbers is : ",end="")
print (a.max(b))
```

输出:

```py
The minimum of two numbers is : 7.429999999999999715782905696
The maximum of two numbers is : 9.529999999999999360511537816
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。