# Python 中的阶乘()

> 原文:[https://www.geeksforgeeks.org/factorial-in-python/](https://www.geeksforgeeks.org/factorial-in-python/)

知道的人不多，但是 python 提供了一个直接的函数，可以计算一个数的阶乘，而不需要编写计算阶乘的全部代码。

**计算阶乘的简单方法**

```py
# Python code to demonstrate naive method
# to compute factorial
n = 23
fact = 1

for i in range(1,n+1):
    fact = fact * i

print ("The factorial of 23 is : ",end="")
print (fact)
```

输出:

```py
The factorial of 23 is : 25852016738884976640000

```

**使用数学因子()**

这个方法是在 python 的**数学**模块中定义的。因为它有 C 型内部实现，所以速度快。

```py
math.factorial(x)
Parameters :
x : The number whose factorial has to be computed.
Return value :
Returns the factorial of desired number.
Exceptions : 
Raises Value error if number is negative or non-integral.

```

```py
# Python code to demonstrate math.factorial()
import math

print ("The factorial of 23 is : ", end="")
print (math.factorial(23))
```

输出:

```py
The factorial of 23 is : 25852016738884976640000

```

**数学中的例外情况.阶乘()**

*   **如果给定的数字是负数:**

    ```py
    # Python code to demonstrate math.factorial()
    # Exceptions ( negative number )

    import math

    print ("The factorial of -5 is : ",end="")

    # raises exception
    print (math.factorial(-5))
    ```

    输出:

    ```py
    The factorial of -5 is : 

    ```

    运行时错误:

    ```py
    Traceback (most recent call last):
      File "/home/f29a45b132fac802d76b5817dfaeb137.py", line 9, in 
        print (math.factorial(-5))
    ValueError: factorial() not defined for negative values

    ```

*   **如果给定的数字是非整数值:**

    ```py
    # Python code to demonstrate math.factorial()
    # Exceptions ( Non-Integral number )

    import math

    print ("The factorial of 5.6 is : ",end="")

    # raises exception
    print (math.factorial(5.6))
    ```

    输出:

    ```py
    The factorial of 5.6 is : 

    ```

    运行时错误:

    ```py
    Traceback (most recent call last):
      File "/home/3987966b8ca9cbde2904ad47dfdec124.py", line 9, in 
        print (math.factorial(5.6))
    ValueError: factorial() only accepts integral values

    ```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。