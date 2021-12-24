# Python 中的 NZEC 错误

> 原文:[https://www.geeksforgeeks.org/nzec-error-python/](https://www.geeksforgeeks.org/nzec-error-python/)

在各种竞争网站编码时，许多人一定遇到过 NZEC 错误。顾名思义，当您的代码未能返回 0 时，就会出现 NZEC(非零退出代码)。当一个代码返回 0 时，意味着它成功地执行了，否则它将根据错误的类型返回一些其他的数字。
当程序结束时，它应该返回“0”来指示是否完成罚款，并且不能这样做，这会导致 NZEC。当然，还有更多与 NZEC 相关的案例。

**为什么会出现 NZEC？(一个例子)**

在 python 中，一般来说，多个输入用逗号分隔，我们使用 input()或 int(input())读取它们，但是大多数在线编码平台在测试时给出的输入用空格分隔，在这些情况下，int(input())无法正确读取输入，并显示像 NZEC 一样的错误。

**如何化解？**

例如，想一个简单的程序，你必须读取 2 个整数并打印它们(在输入文件中，两个整数在同一行)。假设您有两个整数，如下所示:
23 45
而不是使用:

```py
n = int(input())
k = int(input())
```

使用:

```py
n, k = raw_input().split(" ")
n = int(n)
k = int(k)
```

用空格分隔输入。

**错误代码**

```py
n = int(input())
k = int(input())
print n," ",k
```

**输入:**
2 3
当您在 [IDE](https://ide.geeksforgeeks.org/) 中使用上述输入运行上述代码时，您将获得错误:-

```py
Traceback (most recent call last):
  File "b712edd81d4a972de2a9189fac8a83ed.py", line 1, in 
    n = int(input())
  File "", line 1
    2 3
      ^
SyntaxError: unexpected EOF while parsing

```

当输入分为两行时，上面的代码可以正常工作。你可以考验一下自己。要克服这个问题，您需要使用 split。

**正确代码**

```py
n, k = raw_input().split(" ")
n = int(n)
k = int(k)
print n," ",k
```

**输入:**

```py
7 3
```

**输出:**

```py
7   3

```

**NZEC 错误的一些突出原因**

1.  无限递归或者堆栈内存不足。
2.  输入和输出与测试用例并不完全相同。
3.  作为在线平台，使用与指定输出完全匹配的计算机代码测试您的程序。
4.  当您的程序执行基本的编程错误(如除以 0)时，也会出现这种类型的错误。
5.  检查变量的值，它们可能容易受到整数流的影响。

NZEC 错误的发生可能还有其他原因，我已经列出了常见的原因。

本文由 **Aakash Tiwari** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。