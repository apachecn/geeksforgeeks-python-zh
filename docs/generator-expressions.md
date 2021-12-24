# Python |生成器表达式

> 原文:[https://www.geeksforgeeks.org/generator-expressions/](https://www.geeksforgeeks.org/generator-expressions/)

在 **Python** 中，为了创建迭代器，我们可以同时使用正则函数和生成器。**生成器**就像普通函数一样编写，但是我们使用 yield()而不是 return()来返回结果。作为实现迭代器的工具，它更强大。实现起来很容易，也更方便，因为它可以按需提供元素评估。与遇到返回语句时完全终止的常规函数不同，生成器使用 yield 语句，在该语句中，函数的状态是从上次调用中保存的，并且可以在下次调用生成器函数时获取或恢复。生成器相对于列表的另一大优势是它占用的内存少得多。

除此之外，还有两个函数 _next_()和 _iter_()使生成器函数更加紧凑和可靠。示例:

## 蟒蛇 3

```py
# Python code to illustrate generator, yield() and next().
def generator():
    t = 1
    print ('First result is ',t)
    yield t

    t += 1
    print ('Second result is ',t)
    yield t

    t += 1
    print('Third result is ',t)
    yield t

call = generator()
next(call)
next(call)
next(call)
```

输出:

```py
First result is  1
Second result is  2
Third result is  3
```

**发电机功能和正常功能的区别–**

*   一旦函数产生，函数将暂停，并将控制权转移给调用方。
*   当函数终止时，在进一步调用时会自动引发停止迭代。
*   局部变量及其状态在连续调用之间被记住。
*   生成器函数包含一个或多个 yield 语句，而不是一个 return 语句。
*   由于像 _next_()和 _iter_()这样的方法是自动实现的，所以我们可以使用 next()迭代这些项。

还有其他各种各样的表达方式，可以像列表理解一样简单地编码，但是我们用括号代替括号。这些表达式是为封闭函数立即使用生成器的情况而设计的。生成器表达式允许创建没有 yield 关键字的生成器。然而，它并不共享用屈服函数创建的发电机的全部功率。示例:

## 蟒蛇 3

```py
# Python code to illustrate generator expression
generator = (num ** 2 for num in range(10))
for num in generator:
    print(num)
```

输出:

```py
0
1
4
9
16
25
36
49
64
81
```

我们还可以使用生成器表达式生成一个列表:

## 蟒蛇 3

```py
string = 'geek'
li = list(string[i] for i in range(len(string)-1, -1, -1))
print(li)
```

输出:

```py
['k', 'e', 'e', 'g']
```

本文由**钦莫伊·蕾恩卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。