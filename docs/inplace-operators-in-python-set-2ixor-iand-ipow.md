# Python 中的 Inplace 运算符|集合 2 (ixor()、ind()、ipow()、…)

> 原文:[https://www . geesforgeks . org/in place-operators-in-python-set-2 ixor-and-ipow/](https://www.geeksforgeeks.org/inplace-operators-in-python-set-2ixor-iand-ipow/)

[Python 中的 Inplace 运算符| Set 1(iadd()、isub()、icon cat()……)](https://www.geeksforgeeks.org/inplace-operators-python-set-1iadd-isub-iconcat/)

本文将讨论更多的函数。

**1。ixor()** :-该功能用于**分配和异或当前值**。该操作执行“ **a^ = b** 操作。对于不可变的容器，如字符串、数字和元组，赋值是**而不是**。

**2。ipow()** :-该功能用于**分配当前值**并求其幂。该操作执行“ **a ** = b** 操作。赋值是**而不是**在不可变容器的情况下执行，如字符串、数字和元组。

```py
# Python code to demonstrate the working of 
# ixor() and ipow()

# importing operator to handle operator operations
import operator

# using ixor() to exclusive or and assign value
x = operator.ixor(10,5);

# printing the modified value
print ("The value after xoring and assigning : ",end="")
print (x)

# using ipow() to exponentiate and assign value
x = operator.ipow(5,4);

# printing the modified value
print ("The value after exponentiating and assigning : ",end="")
print (x)
```

输出:

```py
The value after xoring and assigning : 15
The value after exponentiating and assigning : 625

```

**3。ind()**:-该函数用于**分配和按位与当前值**。该操作执行“ **a & = b** 操作。对于不可变的容器，如字符串、数字和元组，赋值是**而不是**。

**4。ior()** :-该函数用于**对当前值**进行赋值和按位 or 运算。该操作执行“ **a |=b** 操作。赋值是**而不是**在不可变容器的情况下执行，如字符串、数字和元组。

```py
# Python code to demonstrate the working of 
# ior() and iand()

# importing operator to handle operator operations
import operator

# using ior() to or, and assign value
x = operator.ior(10,5);

# printing the modified value
print ("The value after bitwise or, and assigning : ",end="")
print (x)

# using iand() to and, and assign value
x = operator.iand(5,4);

# printing the modified value
print ("The value after bitwise and, and assigning : ",end="")
print (x)
```

输出:

```py
The value after bitwise or, and assigning : 15
The value after bitwise and, and assigning : 4

```

**5。ilshift()** :-该函数用于通过第二个参数对当前值进行**赋值和按位左移位。该操作执行“ **a < < =b** 操作。对于不可变的容器，如字符串、数字和元组，赋值是**而不是**。**

**6。irshift()** :-该函数用于通过第二个参数对当前值进行**赋值和按位右移。该操作执行“ **a > > =b** 操作。赋值是**而不是**在不可变容器的情况下执行，如字符串、数字和元组。**

```py
# Python code to demonstrate the working of 
# ilshift() and irshift()

# importing operator to handle operator operations
import operator

# using ilshift() to bitwise left shift and assign value
x = operator.ilshift(8,2);

# printing the modified value
print ("The value after bitwise left shift and assigning : ",end="")
print (x)

# using irshift() to bitwise right shift and assign value
x = operator.irshift(8,2);

# printing the modified value
print ("The value after bitwise right shift and assigning : ",end="")
print (x)
```

输出:

```py
The value after bitwise left shift and assigning : 32
The value after bitwise right shift and assigning : 2

```

下一篇文章–[现场对标准操作员](https://www.geeksforgeeks.org/inplace-vs-standard-operators-python/)

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。