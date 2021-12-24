# Python 中的复数|集合 2(重要函数和常数)

> 原文:[https://www . geesforgeks . org/complex-numbers-python-set-2-important-functions-constants/](https://www.geeksforgeeks.org/complex-numbers-python-set-2-important-functions-constants/)

python 复数介绍:[Python 中的复数|集合 1(简介)](https://www.geeksforgeeks.org/complex-numbers-in-python-set-1-introduction/)
本文讨论了一些更重要的函数和常数。
**复数运算**:

**1。exp()** :-这个函数返回参数中提到的复数的**指数**。

**2。log(x，b)** :-这个函数返回 x 的**对数值，基数为 b** ，两者都在它的参数中提到。如果未指定基数，则返回 x 的自然对数。

```
# Python code to demonstrate the working of 
# exp(), log()

# importing "cmath" for complex number operations
import cmath
import math

# Initializing real numbers
x = 1.0
y = 1.0

# converting x and y into complex number
z = complex(x, y);

# printing exponent of complex number
print ("The exponent of complex number is : ", end="")
print (cmath.exp(z))

# printing log form of complex number
print ("The log(base 10) of complex number is : ", end="")
print (cmath.log(z,10))
```

输出:

```
The exponent of complex number is : (1.4686939399158851+2.2873552871788423j)
The log(base 10) of complex number is : (0.15051499783199057+0.3410940884604603j)

```

**3。log10()** :-该函数返回复数的**对数基数 10** 。

**4。sqrt()** :-这将计算复数的**平方根**。

```
# Python code to demonstrate the working of 
# log10(), sqrt()
# importing "cmath" for complex number operations
import cmath
import math

# Initializing real numbers
x = 1.0
y = 1.0

# converting x and y into complex number
z = complex(x, y);

# printing log10 of complex number
print ("The log10 of complex number is : ", end="")
print (cmath.log10(z))

# printing square root form of complex number
print ("The square root of complex number is : ", end="")
print (cmath.sqrt(z))
```

输出:

```
The log10 of complex number is : (0.15051499783199057+0.3410940884604603j)
The square root of complex number is : (1.09868411346781+0.45508986056222733j)

```

**5。is inite()**:-如果复数的实部和虚部都是**有限的**，则返回**真，否则返回假。**

**6。isinf()** :-如果复数的实部或虚部为/为**无穷大**，则返回**真，否则返回假。**

**7。isnan()** :-如果复数的**实部或虚部**为 **NaN** ，则返回 true，否则返回 false。

```
# Python code to demonstrate the working of 
# isnan(), isinf(), isfinite()

# importing "cmath" for complex number operations
import cmath
import math

# Initializing real numbers
x = 1.0
y = 1.0
a = math.inf
b = math.nan

# converting x and y into complex number
z = complex(x,y);

# converting x and a into complex number
w = complex(x,a);

# converting x and b into complex number
v = complex(x,b);

# checking if both numbers are finite
if cmath.isfinite(z):
       print ("Complex number is finite")
else : print ("Complex number is infinite")   

# checking if either number is/are infinite
if cmath.isinf(w):
       print ("Complex number is infinite")
else : print ("Complex number is finite")   

# checking if either number is/are infinite
if cmath.isnan(v):
       print ("Complex number is NaN")
else : print ("Complex number is not NaN") 
```

输出:

```
Complex number is finite
Complex number is infinite
Complex number is NaN

```

**常数**

cmath 模块中定义了两个常量，**“pi”**，返回 pi 的数值。第二个是**“e”**，返回指数的数值。

```
# Python code to demonstrate the working of 
# pi and e 

# importing "cmath" for complex number operations
import cmath
import math

# printing the value of pi 
print ("The value of pi is : ", end="")
print (cmath.pi)

# printing the value of e
print ("The value of exponent is : ", end="")
print (cmath.e)
```

输出:

```
The value of pi is : 3.141592653589793
The value of exponent is : 2.718281828459045

```

[Python 中的复数|集合 3(三角函数和双曲函数)](https://www.geeksforgeeks.org/complex-numbers-in-python-set-3-trigonometric-and-hyperbolic-functions/)

本文由供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。