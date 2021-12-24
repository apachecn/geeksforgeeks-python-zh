# Python 中的精确处理

> 原文:[https://www.geeksforgeeks.org/precision-handling-python/](https://www.geeksforgeeks.org/precision-handling-python/)

Python 在其定义中允许使用不同的函数以多种方式处理浮点数的精度。大部分都是在“**数学**模块下定义的。本文讨论了一些最常用的操作。

1.  **trunc():-** 该函数用于**消除浮点数的所有小数**部分，返回没有小数部分的整数。
2.  **ceil():-** 该功能用于打印大于给定数的**最小整数。**
3.  **floor():-** 此功能用于打印小于给定整数的**最大整数。** 

## 蟒蛇 3

```py
# Python code to demonstrate ceil(), trunc()
# and floor()

# importing "math" for precision function
import math

# initializing value
a = 3.4536

# using trunc() to print integer after truncating
print("The integral value of number is : ", end="")
print(math.trunc(a))

# using ceil() to print number after ceiling
print("The smallest integer greater than number is : ", end="")
print(math.ceil(a))

# using floor() to print number after flooring
print("The greatest integer smaller than number is : ", end="")
print(math.floor(a))
```

输出:

```py
The integral value of number is : 3
The smallest integer greater than number is : 4
The greatest integer smaller than number is : 3
```

**Setting Precision**

有许多方法可以设置浮点值的精度。其中一些将在下面讨论。

1.  **使用“%”:-**“%”运算符在 python 中用于格式化和设置精度。这类似于 [C 编程](https://www.geeksforgeeks.org/c/)中的“printf”语句。
2.  **使用 format():-** 这是另一种格式化字符串以设置精度的方法。
3.  **使用 round(x，n):-** 这个函数接受 2 个参数、**数字**、**和我们想要小数部分舍入到的数字。**

## 蟒蛇 3

```py
# Python code to demonstrate precision
# and round()

# initializing value
a = 3.4536

# using "%" to print value till 2 decimal places
print ("The value of number till 2 decimal place(using %) is : ",end="")
print ('%.2f'%a)

# using format() to print value till 2 decimal places
print ("The value of number till 2 decimal place(using format()) is : ",end="")
print ("{0:.2f}".format(a))

# using round() to print value till 2 decimal places
print ("The value of number till 2 decimal place(using round()) is : ",end="")
print (round(a,2))
```

**输出:**

```py
The value of number till 2 decimal place(using %) is : 3.45
The value of number till 2 decimal place(using format()) is : 3.45
The value of number till 2 decimal place(using round()) is : 3.45
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。