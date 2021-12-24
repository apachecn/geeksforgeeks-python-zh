# Python 中的数学函数|集合 3(三角函数和角函数)

> 原文:[https://www . geesforgeks . org/数学-python 中的函数-集合-3-三角函数和角函数/](https://www.geeksforgeeks.org/mathematical-functions-in-python-set-3-trigonometric-and-angular-functions/)

一些数学函数在下面的集合 1 和集合 2 中讨论

[Python 中的数学函数|集合 1(数值函数)](https://www.geeksforgeeks.org/mathematical-functions-python-set-1-numeric-functions/)
[Python 中的数学函数|集合 2(对数和幂函数)](https://www.geeksforgeeks.org/mathematical-functions-python-set-2-logarithmic-power-functions/)

本文讨论三角函数和角函数。

**1。sin()** :-该函数返回作为参数传递的值的**正弦**。这个函数传递的值应该是**弧度**。

**2。cos()** :-该函数返回作为参数传递的值的**余弦**。这个函数传递的值应该是**弧度**。

```py
# Python code to demonstrate the working of
# sin() and cos()

# importing "math" for mathematical operations
import math

a = math.pi/6

# returning the value of sine of pi/6
print ("The value of sine of pi/6 is : ", end="")
print (math.sin(a))

# returning the value of cosine of pi/6
print ("The value of cosine of pi/6 is : ", end="")
print (math.cos(a))
```

输出:

```py
The value of sine of pi/6 is : 0.49999999999999994
The value of cosine of pi/6 is : 0.8660254037844387

```

**3。tan()** :-该函数返回作为参数传递的值的**正切值**。这个函数传递的值应该是**弧度**。

**4。海波(a，b)** :-返回参数中传递的值的**斜边**。数值上，它返回 **sqrt(a*a + b*b)** 的值。

```py
# Python code to demonstrate the working of
# tan() and hypot()

# importing "math" for mathematical operations
import math

a = math.pi/6
b = 3
c = 4

# returning the value of tangent of pi/6
print ("The value of tangent of pi/6 is : ", end="")
print (math.tan(a))

# returning the value of hypotenuse of 3 and 4
print ("The value of hypotenuse of 3 and 4 is : ", end="")
print (math.hypot(b,c))
```

输出:

```py
The value of tangent of pi/6 is : 0.5773502691896257
The value of hypotenuse of 3 and 4 is : 5.0

```

**5。degrees()** :-该函数用于**将参数值从弧度转换为度数**。

**6。弧度()** :-该函数用于**将参数值从度数转换为弧度**。

```py
# Python code to demonstrate the working of
# degrees() and radians()

# importing "math" for mathematical operations
import math

a = math.pi/6
b = 30

# returning the converted value from radians to degrees
print ("The converted value from radians to degrees is : ", end="")
print (math.degrees(a))

# returning the converted value from degrees to radians
print ("The converted value from degrees to radians is : ", end="")
print (math.radians(b))
```

输出:

```py
The converted value from radians to degrees is : 29.999999999999996
The converted value from degrees to radians is : 0.5235987755982988

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。