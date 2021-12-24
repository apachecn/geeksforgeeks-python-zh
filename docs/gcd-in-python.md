# Python 中的 gcd()

> 原文:[https://www.geeksforgeeks.org/gcd-in-python/](https://www.geeksforgeeks.org/gcd-in-python/)

最高公因数(HCF)，也称为 gcd，可以在 python 中使用**数学**模块提供的单个函数来计算，因此可以在许多情况下使任务变得更容易。

**计算 gcd 的简单方法***   **Using [Recursion](https://www.geeksforgeeks.org/recursion/):

    ```py
    # Python code to demonstrate naive
    # method to compute gcd ( recursion )

    def hcfnaive(a,b):
        if(b==0):
            return a
        else:
            return hcfnaive(b,a%b)

    a = 60
    b= 48

    # prints 12
    print ("The gcd of 60 and 48 is : ",end="")
    print (hcfnaive(60,48))
    ```

    输出:

    ```py
    The gcd of 60 and 48 is : 12

    ```** *   ****Using [Loops](https://www.geeksforgeeks.org/loops-in-python/)

    ```py
    # Python code to demonstrate naive
    # method to compute gcd ( Loops )

    def computeGCD(x, y):

        if x > y:
            small = y
        else:
            small = x
        for i in range(1, small+1):
            if((x % i == 0) and (y % i == 0)):
                gcd = i

        return gcd

    a = 60
    b= 48

    # prints 12
    print ("The gcd of 60 and 48 is : ",end="")
    print (computeGCD(60,48))
    ```

    输出:

    ```py
    The gcd of 60 and 48 is : 12

    ```**** *   ******Using [Euclidean Algorithm](https://www.geeksforgeeks.org/basic-and-extended-euclidean-algorithms/)

    ```py
    # Python code to demonstrate naive
    # method to compute gcd ( Euclidean algo )

    def computeGCD(x, y):

       while(y):
           x, y = y, x % y

       return x

    a = 60
    b= 48

    # prints 12
    print ("The gcd of 60 and 48 is : ",end="")
    print (computeGCD(60,48))
    ```

    输出:

    ```py
    The gcd of 60 and 48 is : 12

    ```

    **使用 Python 的 math.gcd()函数**
    使用 gcd()只需一行就可以计算出相同的 gcd。

    ```py
    math.gcd( x, y )
    Parameters : 
    x :  Non-negative integer whose gcd has to be computed.
    y : Non-negative integer whose gcd has to be computed.
    Return Value : 
    This method will return an absolute/positive integer value after 
    calculating the GCD of given parameters x and y.
    Exceptions : 
    When Both x and y are 0, function returns 0, If any number is a character ,
    Type error is raised.

    ```

    ```py
    # Python code to demonstrate gcd()
    # method to compute gcd

    import math

    # prints 12
    print ("The gcd of 60 and 48 is : ",end="")
    print (math.gcd(60,48))
    ```

    输出:

    ```py
    The gcd of 60 and 48 is : 12

    ```

    **常见异常**
    此功能中的一些常见异常有:

    *   两个数字都是 0，gcd 是 0
    *   如果只有一个数字不是数字，则会引发类型错误。

    ```py
    # Python code to demonstrate gcd()
    # method exceptions

    import math

    # prints 0
    print ("The gcd of 0 and 0 is : ",end="")
    print (math.gcd(0,0))

    # Produces error
    print ("The gcd of a and 13 is : ",end="")
    print (math.gcd('a',13))
    ```

    输出:

    ```py
    The gcd of 0 and 0 is : 0
    The gcd of a and 13 is : 

    ```

    运行时错误:

    ```py
    Traceback (most recent call last):
      File "/home/94493cdfb3c8509146254862d12bcc97.py", line 12, in 
        print (math.gcd('a',13))
    TypeError: 'str' object cannot be interpreted as an integer

    ```

    本文由[](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

    **如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。********