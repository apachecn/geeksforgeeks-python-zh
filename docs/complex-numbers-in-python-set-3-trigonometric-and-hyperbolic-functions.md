# Python 中的复数|集合 3(三角函数和双曲函数)

> 原文:[https://www . geesforgeks . org/python 中的复数-集合-3-三角和双曲函数/](https://www.geeksforgeeks.org/complex-numbers-in-python-set-3-trigonometric-and-hyperbolic-functions/)

一些重要的复数函数将在下面的文章中讨论

[Python 中的复数|集合 1(简介)](https://www.geeksforgeeks.org/complex-numbers-in-python-set-1-introduction/)
[Python 中的复数|集合 2(重要函数和常数)](https://www.geeksforgeeks.org/complex-numbers-python-set-2-important-functions-constants/)

本文讨论三角函数和双曲函数。

**三角函数**

**1。sin()** :这个函数返回参数中传递的复数的**正弦**。

**2。cos()** :这个函数返回参数中传递的复数的**余弦**。

**3。tan()** :此函数返回参数中传递的复数的**正切值**。

```py
# Python code to demonstrate the working of 
# sin(), cos(), tan()

# importing "cmath" for complex number operations
import cmath

# Initializing real numbers
x = 1.0

y = 1.0

# converting x and y into complex number z
z = complex(x,y);

# printing sine of the complex number
print ("The sine value of complex number is : ",end="")
print (cmath.sin(z))

# printing cosine of the complex number
print ("The cosine value of complex number is : ",end="")
print (cmath.cos(z))

# printing tangent of the complex number
print ("The tangent value of complex number is : ",end="")
print (cmath.tan(z))
```

输出:

```py
The sine value of complex number is : (1.2984575814159773+0.6349639147847361j)
The cosine value of complex number is : (0.8337300251311491-0.9888977057628651j)
The tangent value of complex number is : (0.2717525853195118+1.0839233273386946j)

```

**4。asin()** :此函数返回参数中传递的复数的**反正弦**。

**5。acos()** :这个函数返回参数中传递的复数的**弧余弦**。

**6。atan()** :此函数返回参数中传递的复数的**反正切**。

```py
# Python code to demonstrate the working of 
# asin(), acos(), atan()

# importing "cmath" for complex number operations
import cmath

# Initializing real numbers
x = 1.0

y = 1.0

# converting x and y into complex number z
z = complex(x,y);

# printing arc sine of the complex number
print ("The arc sine value of complex number is : ",end="")
print (cmath.asin(z))

# printing arc cosine of the complex number
print ("The arc cosine value of complex number is : ",end="")
print (cmath.acos(z))

# printing arc tangent of the complex number
print ("The arc tangent value of complex number is : ",end="")
print (cmath.atan(z))
```

输出:

```py
The arc sine value of complex number is : (0.6662394324925153+1.0612750619050357j)
The arc cosine value of complex number is : (0.9045568943023814-1.0612750619050357j)
The arc tangent value of complex number is : (1.0172219678978514+0.40235947810852507j)

```

**双曲函数**

**1。sinh()** :这个函数返回参数中传递的复数的**双曲正弦**。

**2。cosh()** :这个函数返回参数中传递的复数的**双曲余弦**。

**3。tanh()** :这个函数返回参数中传递的复数的**双曲正切**。

```py
# Python code to demonstrate the working of 
# sinh(), cosh(), tanh()

# importing "cmath" for complex number operations
import cmath

# Initializing real numbers
x = 1.0

y = 1.0

# converting x and y into complex number z
z = complex(x,y);

# printing hyperbolic sine of the complex number
print ("The hyperbolic sine value of complex number is : ",end="")
print (cmath.sinh(z))

# printing hyperbolic cosine of the complex number
print ("The hyperbolic cosine value of complex number is : ",end="")
print (cmath.cosh(z))

# printing hyperbolic tangent of the complex number
print ("The hyperbolic tangent value of complex number is : ",end="")
print (cmath.tanh(z))
```

输出:

```py
The hyperbolic sine value of complex number is : (0.6349639147847361+1.2984575814159773j)
The hyperbolic cosine value of complex number is : (0.8337300251311491+0.9888977057628651j)
The hyperbolic tangent value of complex number is : (1.0839233273386946+0.2717525853195117j)

```

**4。asinh()** :这个函数返回参数中传递的复数的**反双曲正弦**。

**5。acosh()** :这个函数返回参数中传递的复数的**反双曲余弦**。

**6。atanh()** :这个函数返回参数中传递的复数的**反双曲正切**。

```py
# Python code to demonstrate the working of 
# asinh(), acosh(), atanh()

# importing "cmath" for complex number operations
import cmath

# Initializing real numbers
x = 1.0

y = 1.0

# converting x and y into complex number z
z = complex(x,y);

# printing inverse hyperbolic sine of the complex number
print ("The inverse hyperbolic sine value of complex number is : ",end="")
print (cmath.asinh(z))

# printing inverse hyperbolic cosine of the complex number
print ("The inverse hyperbolic cosine value of complex number is : ",end="")
print (cmath.acosh(z))

# printing inverse hyperbolic tangent of the complex number
print ("The inverse hyperbolic tangent value of complex number is : ",end="")
print (cmath.atanh(z))
```

输出:

```py
The inverse hyperbolic sine value of complex number is : (1.0612750619050357+0.6662394324925153j)
The inverse hyperbolic cosine value of complex number is : (1.0612750619050357+0.9045568943023813j)
The inverse hyperbolic tangent value of complex number is : (0.40235947810852507+1.0172219678978514j)

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。