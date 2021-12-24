# Python 中的部分函数

> 原文:[https://www.geeksforgeeks.org/partial-functions-python/](https://www.geeksforgeeks.org/partial-functions-python/)

部分函数允许我们固定函数的一定数量的参数，并生成一个新的函数。

**例:**

```
from functools import partial

# A normal function
def f(a, b, c, x):
    return 1000*a + 100*b + 10*c + x

# A partial function that calls f with
# a as 3, b as 1 and c as 4.
g = partial(f, 3, 1, 4)

# Calling g()
print(g(5))
```

**输出:**

```
3145

```

在这个例子中，我们用 a、b 和 c 的常量值预先填充了我们的函数，g()只接受一个参数，即变量 x。

**另一个例子:**

```
from functools import *

# A normal function
def add(a, b, c):
    return 100 * a + 10 * b + c

# A partial function with b = 1 and c = 2
add_part = partial(add, c = 2, b = 1)

# Calling partial function
print(add_part(3))
```

**输出:**

```
312

```

*   Local functions can be used to derive specialized functions from general functions, thus helping us to reuse code.
*   This function is similar to [binding](https://www.geeksforgeeks.org/bind-function-placeholders-c/) in C++.

本文由 **Mayank Rawat** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。