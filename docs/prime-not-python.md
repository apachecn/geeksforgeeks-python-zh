# Python 中的 Prime 与否

> 原文:[https://www.geeksforgeeks.org/prime-not-python/](https://www.geeksforgeeks.org/prime-not-python/)

每个程序员都会遇到检查一个数是否是质数的问题，实际上它是任何语言的基本程序之一。我也尝试了许多不同的语言，但我发现实现它的最佳语言是 Python。只有一行，程序就完成了所有的工作。它比其他语言简单流畅。

[Any and All](https://www.geeksforgeeks.org/any-all-in-python/) 的概念确实将这个问题简化为一条线，是的，它也很快。
本程序使用的逻辑基于[校法查质数](https://www.geeksforgeeks.org/primality-test-set-1-introduction-and-school-method/)。

```
# Returns true if n is prime else false
def prime(n):
    return all([(n % j) for j in range(2, int(n**0.5)+1)]) and n>1

# Driver code
n = 41
if prime(n):
       print("Yes")
else:
    print("No")
```

```
Yes

```

本文由**钦莫伊·蕾恩卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。