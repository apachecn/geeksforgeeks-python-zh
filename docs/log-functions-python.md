# Python 中的日志函数

> 原文:[https://www.geeksforgeeks.org/log-functions-python/](https://www.geeksforgeeks.org/log-functions-python/)

Python 在模块“**数学**下提供了许多内置对数函数，允许我们使用一行来计算日志。对数函数有 4 种变体，本文将对它们进行讨论。
T3】1。log(a，(Base)) : 此函数用于计算 a 的**自然对数** (Base e)。如果传递了 2 个参数，它将计算参数 a 的期望基数的对数，数值为 **log(a)/log(Base)** 。

```py
Syntax :
math.log(a,Base)
Parameters : 
a : The numeric value
Base :  Base to which the logarithm has to be computed.
Return Value : 
Returns natural log if 1 argument is passed and log with
specified base if 2 arguments are passed.
Exceptions : 
Raises ValueError if a negative no. is passed as argument.
```

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# log(a,Base)

import math

# Printing the log base e of 14
print ("Natural logarithm of 14 is : ", end="")
print (math.log(14))

# Printing the log base 5 of 14
print ("Logarithm base 5 of 14 is : ", end="")
print (math.log(14,5))
```

**输出:**

```py
Natural logarithm of 14 is : 2.6390573296152584
Logarithm base 5 of 14 is : 1.6397385131955606
```

**2。log2(a) :** 该函数用于计算 a 的**对数底数 2** ，显示比 log(a，2)更准确的结果。

```py
Syntax :
math.log2(a)
Parameters : 
a : The numeric value
Return Value : 
Returns logarithm base 2 of a
Exceptions : 
Raises ValueError if a negative no. is passed as argument.
```

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# log2(a)

import math

# Printing the log base 2 of 14
print ("Logarithm base 2 of 14 is : ", end="")
print (math.log2(14))
```

**输出:**

```py
Logarithm base 2 of 14 is : 3.807354922057604
```

**3。log10(a) :** 该函数用于计算 a 的**对数底数 10** ，显示比 log(a，10)更准确的结果。

```py
Syntax :
math.log10(a)
Parameters : 
a : The numeric value
Return Value : 
Returns logarithm base 10 of a
Exceptions : 
Raises ValueError if a negative no. is passed as argument.
```

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# log10(a)

import math

# Printing the log base 10 of 14
print ("Logarithm base 10 of 14 is : ", end="")
print (math.log10(14))
```

**输出:**

```py
Logarithm base 10 of 14 is : 1.146128035678238
```

**3。log1p(a) :** 该函数用于计算**对数(1+a)** 。

```py
Syntax :
math.log1p(a)
Parameters : 
a : The numeric value
Return Value : 
Returns log(1+a)
Exceptions : 
Raises ValueError if a negative no. is passed as argument.
```

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# log1p(a)

import math

# Printing the log(1+a) of 14
print ("Logarithm(1+a) value of 14 is : ", end="")
print (math.log1p(14))
```

**输出:**

```py
Logarithm(1+a) value of 14 is : 2.70805020110221
```

**Exception**

**1。值错误:**如果数字为**负数**，则该函数返回值错误。

## 蟒蛇 3

```py
# Python code to demonstrate the Exception of
# log(a)

import math

# Printing the log(a) of -14
# Throws Exception
print ("log(a) value of -14 is : ", end="")
print (math.log(-14))
```

**输出:**

```py
log(a) value of -14 is : 
```

**运行时错误:**

```py
Traceback (most recent call last):
  File "/home/8a74e9d7e5adfdb902ab15712cbaafe2.py", line 9, in 
    print (math.log(-14))
ValueError: math domain error
```

**Practical Application**

log10()函数的应用之一是用来计算一个数字的**位数。下面的代码说明了同样的情况。**

## 蟒蛇 3

```py
# Python code to demonstrate the Application of
# log10(a)

import math

# Printing no. of  digits in 73293
print ("The number of digits in 73293 are : ", end="")
print (int(math.log10(73293) + 1))
```

**输出:**

```py
The number of digits in 73293 are : 5
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。