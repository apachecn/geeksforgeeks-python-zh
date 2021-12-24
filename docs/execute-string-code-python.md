# 用 Python 执行一串代码

> 原文:[https://www.geeksforgeeks.org/execute-string-code-python/](https://www.geeksforgeeks.org/execute-string-code-python/)

给定字符串变量中的几行代码，并执行字符串中的代码。
示例:

```py
Input:
code = """ a = 6+5
           print(a)"""
Output:
11
Explanation:
Mind it that "code" is a variable and
not python code. It contains another code, 
which we need to execute.

Input:
code = """ def factorial(num):
               for i in range(1,num+1):
                   fact = fact*i
               return fact
           print(factorial(5))"""
Output:
120
Explanation:
On executing the program cantaining the 
variable in Python we must get the result 
after executing the content of the variable.
```

这里我们使用 [**exec()**](https://www.geeksforgeeks.org/exec-in-python/) 函数来求解变量内部包含的代码。exec()函数用于 Python 代码的动态执行。它可以包含一个包含 Python 语句的代码块，如循环、类、函数/方法定义，甚至 try/except 块。这个函数不返回任何东西。下面的代码解决了这个问题，并解释了 exec()函数。

## 蟒蛇 3

```py
# Python program to illustrate use of exec to
# execute a given code as string.

# function illustrating how exec() functions.
def exec_code():
    LOC = """
def factorial(num):
    fact=1
    for i in range(1,num+1):
        fact = fact*i
    return fact
print(factorial(5))
"""
    exec(LOC)

# Driver Code
exec_code()
```

输出:

```py
120
```

本文由 [**【钦莫伊蕾恩卡】**](https://www.linkedin.com/in/lenkachinmoy/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。