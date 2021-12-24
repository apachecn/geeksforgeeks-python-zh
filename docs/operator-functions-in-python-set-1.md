# Python 中的运算符函数|集合 1

> 原文:[https://www . geesforgeks . org/operator-functions-in-python-set-1/](https://www.geeksforgeeks.org/operator-functions-in-python-set-1/)

Python 在模块“运算符”下为许多数学、逻辑、关系、按位等运算提供了预定义的函数。本文介绍了一些基本功能。

**1。添加(a，b)** :-该函数返回给定参数的**加法**。
操作–**a+b .**

**2。sub(a，b)** :-该函数返回给定参数的**差值**。
操作–**a–b .**

**3。mul(a，b)** :-该函数返回给定参数的**乘积**。
操作–**a * b .**

```py
# Python code to demonstrate working of 
# add(), sub(), mul()

# importing operator module 
import operator

# Initializing variables
a = 4

b = 3

# using add() to add two numbers
print ("The addition of numbers is :",end="");
print (operator.add(a, b))

# using sub() to subtract two numbers
print ("The difference of numbers is :",end="");
print (operator.sub(a, b))

# using mul() to multiply two numbers
print ("The product of numbers is :",end="");
print (operator.mul(a, b))
```

输出:

```py
The addition of numbers is:7
The difference of numbers is :1
The product of numbers is:12

```

**4。truediv(a，b)** :-该函数返回给定参数的**除法**。
操作–**a/b .**

**5。floordiv(a，b)** :-这个函数也返回给定参数的除法。但是该值是地板值，即**返回最大的小整数**。
操作–**a//b .**

**6。幂(a，b)** :-该函数返回给定参数的**幂**。
操作–**a * * b .**

**7。mod(a，b)** :-该函数返回给定参数的**模数**。
操作–**a % b .**

```py
# Python code to demonstrate working of 
# truediv(), floordiv(), pow(), mod()

# importing operator module 
import operator

# Initializing variables
a = 5

b = 2

# using truediv() to divide two numbers
print ("The true division of numbers is : ",end="");
print (operator.truediv(a,b))

# using floordiv() to divide two numbers
print ("The floor division of numbers is : ",end="");
print (operator.floordiv(a,b))

# using pow() to exponentiate two numbers
print ("The exponentiation of numbers is : ",end="");
print (operator.pow(a,b))

# using mod() to take modulus of two numbers
print ("The modulus of numbers is : ",end="");
print (operator.mod(a,b))
```

输出:

```py
The true division of numbers is: 2.5
The floor division of numbers is: 2
The exponentiation of numbers is: 25
The modulus of numbers is: 1

```

**8。lt(a，b)** :-该功能用于**检查 a 是否小于 b**。如果 a 小于 b，则返回 true，否则返回 false。
操作–**a<b**。

**9。le(a，b)** :-该功能用于**检查 a 是否小于或等于 b**。如果 a 小于或等于 b，则返回 true，否则返回 false。
操作–**a<= b**。

**10。等式(a，b)** :-该功能用于**检查 a 是否等于 b**。如果 a 等于 b，则返回 true，否则返回 false。
操作–**a = = b**。

```py
# Python code to demonstrate working of 
# lt(), le() and eq()

# importing operator module 
import operator

# Initializing variables
a = 3

b = 3

# using lt() to check if a is less than b
if(operator.lt(a,b)):
       print ("3 is less than 3")
else : print ("3 is not less than 3")

# using le() to check if a is less than or equal to b
if(operator.le(a,b)):
       print ("3 is less than or equal to 3")
else : print ("3 is not less than or equal to 3")

# using eq() to check if a is equal to b
if (operator.eq(a,b)):
       print ("3 is equal to 3")
else : print ("3 is not equal to 3")
```

输出:

```py
3 is not less than 3
3 is less than or equal to 3
3 is equal to 3

```

**11 时。gt(a，b)** :-该功能用于**检查 a 是否大于 b**。如果 a 大于 b，则返回 true，否则返回 false。
操作–**a>b**。

**12 时。ge(a，b)** :-该功能用于**检查 a 是否大于或等于 b**。如果 a 大于或等于 b，则返回 true，否则返回 false。
操作–**a>= b**。

**13。ne(a，b)** :-该功能用于**检查 a 是否不等于 b 或等于**。如果 a 不等于 b，则返回 true，否则返回 false。
行动–**a！= b** 。

```py
# Python code to demonstrate working of 
# gt(), ge() and ne()

# importing operator module 
import operator

# Initializing variables
a = 4

b = 3

# using gt() to check if a is greater than b
if (operator.gt(a,b)):
       print ("4 is greater than 3")
else : print ("4 is not greater than 3")

# using ge() to check if a is greater than or equal to b
if (operator.ge(a,b)):
       print ("4 is greater than or equal to 3")
else : print ("4 is not greater than or equal to 3")

# using ne() to check if a is not equal to b
if (operator.ne(a,b)):
       print ("4 is not equal to 3")
else : print ("4 is equal to 3")
```

输出:

```py
4 is greater than 3
4 is greater than or equal to 3
4 is not equal to 3

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。