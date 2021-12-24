# Python 中的数学函数|集合 2(对数和幂函数)

> 原文:[https://www . geesforgeks . org/数学-函数-python-set-2-对数-幂-函数/](https://www.geeksforgeeks.org/mathematical-functions-python-set-2-logarithmic-power-functions/)

数字函数在下面的第 1 集中讨论

[Python 中的数学函数|集合 1(数值函数)](https://www.geeksforgeeks.org/mathematical-functions-python-set-1-numeric-functions/)

对数函数和幂函数在本套中讨论。

**1。exp(a)** :-该函数将 **e 的值加到幂 a (e**a)** 上。

**2。log(a，b)** :-该函数返回以 b 为基数的 a 的对数**值**。如果未提及基数，则计算值为自然对数。

```py
# Python code to demonstrate the working of
# exp() and log()

# importing "math" for mathematical operations
import math

# returning the exp of 4
print ("The e**4 value is : ", end="")
print (math.exp(4))

# returning the log of 2,3
print ("The value of log 2 with base 3 is : ", end="")
print (math.log(2,3))
```

输出:

```py
The e**4 value is : 54.598150033144236
The value of log 2 with base 3 is : 0.6309297535714574

```

**3。log2(a)** :-该函数计算基数为 2 的 **log a 的值。这个值比上面讨论的函数值**更准确**。**

**4。log10(a)** :-该函数计算基数为 10 的 **log a 的值。该值比上述函数的值**更准确**。**

```py
# Python code to demonstrate the working of
# log2() and log10()

# importing "math" for mathematical operations
import math

# returning the log2 of 16
print ("The value of log2 of 16 is : ", end="")
print (math.log2(16))

# returning the log10 of 10000
print ("The value of log10 of 10000 is : ", end="")
print (math.log10(10000))
```

输出:

```py
The value of log2 of 16 is : 4.0
The value of log10 of 10000 is : 4.0

```

**5。功率(a，b)** :-该函数用于计算 **a 提升到功率 b (a**b)** 的值。

**6。sqrt()** :-该函数返回数字的**平方根**。

```py
# Python code to demonstrate the working of
# pow() and sqrt()

# importing "math" for mathematical operations
import math

# returning the value of 3**2
print ("The value of 3 to the power 2 is : ", end="")
print (math.pow(3,2))

# returning the square root of 25
print ("The value of square root of 25 : ", end="")
print (math.sqrt(25))
```

输出:

```py
The value of 3 to the power 2 is : 9.0
The value of square root of 25 : 5.0

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。