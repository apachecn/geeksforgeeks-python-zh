# Python 中的数学函数|集合 4(特殊函数和常数)

> 原文:[https://www . geesforgeks . org/数学-python 中的函数-集合-4-特殊函数和常数/](https://www.geeksforgeeks.org/mathematical-functions-in-python-set-4-special-functions-and-constants/)

下面的集合 1、集合 2 和集合 3 中讨论了一些数学函数
[Python 中的数学函数|集合 1(数值函数)](https://www.geeksforgeeks.org/mathematical-functions-python-set-1-numeric-functions/)
[Python 中的数学函数|集合 2(对数和幂函数)](https://www.geeksforgeeks.org/mathematical-functions-python-set-2-logarithmic-power-functions/)
[Python 中的数学函数|集合 3(三角和角函数)](https://www.geeksforgeeks.org/mathematical-functions-in-python-set-3-trigonometric-and-angular-functions/)

本文讨论特殊函数和常数。

**1。gamma()** :-该函数用于返回参数的 **gamma 函数**。

```py
# Python code to demonstrate the working of
# gamma()

# importing "math" for mathematical operations
import math

a = 4

# returning the gamma() of 4
print ("The gamma() of 4 is : ", end="")
print (math.gamma(a))
```

输出:

```py
The gamma() of 4 is : 6.0

```

**2。pi** :-这是一个内置常数，输出 pi(3.141592) 的**值。**

**3。e** :-这是一个内置常数，输出 e(2.718281) 的**值。**

```py
# Python code to demonstrate the working of
# const. pi and e

# importing "math" for mathematical operations
import math

# returning the value of const. pi
print ("The value of const. pi is : ", end="")
print (math.pi)

# returning the value of const. e
print ("The value of const. e is : ", end="")
print (math.e)
```

输出:

```py
The value of const. pi is : 3.141592653589793
The value of const. e is : 2.718281828459045

```

**4。inf** :-这是一个**正浮点无穷大常量**。-inf 用于表示负浮点无穷大。这个常量在 python 3.5 及更高版本中定义。

**5。isinf()** :-该功能用于**检查**值是否为**无穷大。**

**6。nan** :-这个常量表示“[不是 python 中的数字](https://www.geeksforgeeks.org/nan-in-cpp-what-is-it-and-how-to-check-for-it/)。这个常量在 python 3.5 及更高版本中定义。

**7。isnan()** :-如果数字为“nan”则此函数返回 **true，否则返回 false。**

```py
# Python code to demonstrate the working of
# inf, nan, isinf(), isnan()

# importing "math" for mathematical operations
import math

# checking if number is nan
if (math.isnan(math.nan)):
       print ("The number is nan")
else : print ("The number is not nan")

# checking if number is positive infinity
if (math.isinf(math.inf)):
       print ("The number is positive infinity")
else : print ("The number is not positive infinity")
```

输出:

```py
The number is nan
The number is positive infinity

```

本文由 **[【曼吉特·辛格】](https://www.geeksforgeeks.org/geek-of-the-month/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。