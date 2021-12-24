# Python 中的就地与标准操作符

> 原文:[https://www . geesforgeks . org/in place-vs-standard-operators-python/](https://www.geeksforgeeks.org/inplace-vs-standard-operators-python/)

现场操作员–[设置 1](https://www.geeksforgeeks.org/inplace-operators-python-set-1iadd-isub-iconcat/) 、[设置 2](https://www.geeksforgeeks.org/inplace-operators-in-python-set-2ixor-iand-ipow/)
普通操作员进行简单的分配工作。另一方面，位置操作符的行为类似于普通操作符**，除了**在可变和不可变目标的情况下，它们的行为方式不同。

*   **_add_** 方法，做简单的加法，取两个参数，返回和，并存储在另一个变量中，不修改任何参数。
*   另一方面， **_iadd_** 方法也接受两个参数，但它通过将总和存储在第一个参数中来对传递的第一个参数进行就地更改。由于这个过程需要对象变异，不可变的目标如数字、字符串和元组，**不应该有 _iadd_ method** 。
*   **普通运算符的“add()”**方法，实现“ **a+b** ”，并将结果存储在上述变量中。
*   **在 place 运算符的“iadd()”**方法中，如果“ **a+=b** ”存在(即在不可变目标的情况下，它不存在)，则实现该方法，并更改传递的参数的值。但是**如果没有，“a+b”就执行**。

**情况 1** : **不可变目标。**
在不可变目标中，如数字、字符串和元组。Inplace 运算符的行为与普通运算符相同，即只进行赋值，不修改传递的参数。

## 计算机编程语言

```
# Python code to demonstrate difference between 
# Inplace and Normal operators in Immutable Targets

# importing operator to handle operator operations
import operator

# Initializing values
x = 5
y = 6
a = 5
b = 6

# using add() to add the arguments passed 
z = operator.add(a,b)

# using iadd() to add the arguments passed 
p = operator.iadd(x,y)

# printing the modified value
print ("Value after adding using normal operator : ",end="")
print (z)

# printing the modified value
print ("Value after adding using Inplace operator : ",end="")
print (p)

# printing value of first argument
# value is unchanged
print ("Value of first argument using normal operator : ",end="")
print (a)

# printing value of first argument
# value is unchanged
print ("Value of first argument using Inplace operator : ",end="")
print (x)
```

输出:

```
Value after adding using normal operator : 11
Value after adding using Inplace operator : 11
Value of first argument using normal operator : 5
Value of first argument using Inplace operator : 5
```

**情况 2** : **可变目标**
可变目标中的 Inplace 运算符的行为，如列表和字典，与普通运算符不同。在目标易变的情况下，**的更新和分配都在**进行。

## 计算机编程语言

```
# Python code to demonstrate difference between 
# Inplace and Normal operators in mutable Targets

# importing operator to handle operator operations
import operator

# Initializing list
a = [1, 2, 4, 5]

# using add() to add the arguments passed 
z = operator.add(a,[1, 2, 3])

# printing the modified value
print ("Value after adding using normal operator : ",end="")
print (z)

# printing value of first argument
# value is unchanged
print ("Value of first argument using normal operator : ",end="")
print (a)

# using iadd() to add the arguments passed 
# performs a+=[1, 2, 3]
p = operator.iadd(a,[1, 2, 3])

# printing the modified value
print ("Value after adding using Inplace operator : ",end="")
print (p)

# printing value of first argument
# value is changed
print ("Value of first argument using Inplace operator : ",end="")
print (a)
```

输出:

```
Value after adding using normal operator : [1, 2, 4, 5, 1, 2, 3]
Value of first argument using normal operator : [1, 2, 4, 5]
Value after adding using Inplace operator : [1, 2, 4, 5, 1, 2, 3]
Value of first argument using Inplace operator : [1, 2, 4, 5, 1, 2, 3]
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。