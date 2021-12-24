# Python 中的数学函数|集合 1(数值函数)

> 原文:[https://www . geesforgeks . org/mathematic-functions-python-set-1-numeric-functions/](https://www.geeksforgeeks.org/mathematical-functions-python-set-1-numeric-functions/)

在 python 中，通过导入一个名为“math”的模块，可以轻松执行许多数学运算，该模块定义了各种函数，使我们的任务变得更容易。

**1。ceil()** :-该函数返回大于数字的**最小整数值。如果数字已经是整数，则返回相同的数字。**

**2。floor()** :-该函数返回小于数字的**最大整数值。如果数字已经是整数，则返回相同的数字。**

```
# Python code to demonstrate the working of
# ceil() and floor()

# importing "math" for mathematical operations
import math

a = 2.3

# returning the ceil of 2.3
print ("The ceil of 2.3 is : ", end="")
print (math.ceil(a))

# returning the floor of 2.3
print ("The floor of 2.3 is : ", end="")
print (math.floor(a))
```

输出:

```
The ceil of 2.3 is : 3
The floor of 2.3 is : 2

```

**3。fabs()** :-该函数返回数字的**绝对值**。

**4。阶乘()** :-该函数返回数字的**阶乘**。如果数字不是整数，将显示一条错误消息。

```
# Python code to demonstrate the working of
# fabs() and factorial()

# importing "math" for mathematical operations
import math

a = -10

b= 5

# returning the absolute value.
print ("The absolute value of -10 is : ", end="")
print (math.fabs(a))

# returning the factorial of 5
print ("The factorial of 5 is : ", end="")
print (math.factorial(b))
```

输出:

```
The absolute value of -10 is : 10.0
The factorial of 5 is : 120

```

**5。copysign(a，b)** :-该函数返回的数字的**值为“a”，但符号为“b”**。返回值是浮点类型。

**6。gcd()** :-该函数用于计算其参数中提到的 2 个数的**最大公约数。这个函数在 python 3.5 及更高版本中工作。**

```
# Python code to demonstrate the working of
# copysign() and gcd()

# importing "math" for mathematical operations
import math

a = -10
b = 5.5
c = 15
d = 5

# returning the copysigned value.
print ("The copysigned value of -10 and 5.5 is : ", end="")
print (math.copysign(5.5, -10))

# returning the gcd of 15 and 5
print ("The gcd of 5 and 15 is : ", end="")
print (math.gcd(5,15))
```

输出:

```
The copysigned value of -10 and 5.5 is : -5.5
The gcd of 5 and 15 is : 5

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。