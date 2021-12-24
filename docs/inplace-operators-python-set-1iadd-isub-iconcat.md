# Python 中的 Inplace 运算符| Set 1 (iadd()、isub()、icon cat()……)

> 原文:[https://www . geesforgeks . org/in place-operators-python-set-1 add-isub-icon cat/](https://www.geeksforgeeks.org/inplace-operators-python-set-1iadd-isub-iconcat/)

Python 在其定义中提供了执行就地操作的方法，即**使用“**运算符**模块在单个语句**中进行赋值和计算。例如

```
x += y is equivalent to x = operator.iadd(x, y) 
```

**一些重要的就地操作**:

**1。iadd()** :-该功能用于**分配和添加当前值**。该操作执行“ **a+=b** 操作。对于不可变的容器，如字符串、数字和元组，赋值是**而不是**。

**2。iconcat()** :-该函数用于在第二个结束时将**串联成一个字符串。**

```
# Python code to demonstrate the working of 
# iadd() and iconcat()

# importing operator to handle operator operations
import operator

# using iadd() to add and assign value
x = operator.iadd(2, 3);

# printing the modified value
print ("The value after adding and assigning : ", end="")
print (x)

# initializing values
y = "geeks"

z = "forgeeks"

# using iconcat() to concat the sequences
y = operator.iconcat(y, z)

# using iconcat() to concat sequences 
print ("The string after concatenation is : ", end="")
print (y)
```

输出:

```
The value after adding and assigning : 5
The string after concatenation is : geeksforgeeks

```

**3。isub()** :-该功能用于**分配和减去当前值**。该操作执行“ **a-=b** 操作。对于不可变的容器，如字符串、数字和元组，赋值是**而不是**。

**4。imul()** :-该功能用于**分配和相乘当前值**。该操作执行“ **a*=b** 操作。赋值是**而不是**在不可变容器的情况下执行，如字符串、数字和元组。

```
# Python code to demonstrate the working of 
# isub() and imul()

# importing operator to handle operator operations
import operator

# using isub() to subtract and assign value
x = operator.isub(2, 3);

# printing the modified value
print ("The value after subtracting and assigning : ", end="")
print (x)

# using imul() to multiply and assign value
x = operator.imul(2, 3);

# printing the modified value
print ("The value after multiplying and assigning : ", end="")
print (x)
```

输出:

```
The value after subtracting and assigning : -1
The value after multiplying and assigning : 6

```

**5。itruediv()** :-该功能用于**分配和分割电流值**。该操作执行“ **a/=b** 操作。对于不可变的容器，如字符串、数字和元组，赋值是**而不是**。

**6。imod()** :-该功能用于**分配并返回余数**。该操作执行“ **a%=b** 操作。赋值是**而不是**在不可变容器的情况下执行，如字符串、数字和元组。

```
# Python code to demonstrate the working of 
# itruediv() and imod()

# importing operator to handle operator operations
import operator

# using itruediv() to divide and assign value
x = operator.itruediv(10, 5);

# printing the modified value
print ("The value after dividing and assigning : ", end="")
print (x)

# using imod() to modulus and assign value
x = operator.imod(10, 6);

# printing the modified value
print ("The value after modulus and assigning : ", end="")
print (x)
```

输出:

```
The value after dividing and assigning : 2.0
The value after modulus and assigning : 4

```

下一篇文章 Python 中的

*   [Position Operator | Episode 2](https://www.geeksforgeeks.org/inplace-operators-in-python-set-2ixor-iand-ipow/)
*   [Position vs Standard Operator](https://www.geeksforgeeks.org/inplace-vs-standard-operators-python/)

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。