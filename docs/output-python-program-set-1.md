# Python 程序输出|第 1 集

> 原文:[https://www.geeksforgeeks.org/output-python-program-set-1/](https://www.geeksforgeeks.org/output-python-program-set-1/)

预测以下 python 程序的输出:

**节目 1:**

```
r = lambda q: q * 2
s = lambda q: q * 3
x = 2
x = r(x)
x = s(x)
x = r(x)
print (x)
```

**输出:**

```
24

```

**说明:**在上面的程序中，r 和 s 是 lambda 函数或匿名函数，q 是这两个函数的自变量。在第一步中，我们已经将 x 初始化为 2。在第二步中，我们将 x 作为参数传递给 lambda 函数 r，这将返回 x*2，它存储在 x 中。也就是说，现在 x = 4。类似地，在第三步中，我们将 x 传递给λ函数 s，因此 x = 4*3。即现在 x = 12。同样在最后一步中，通过将 x 传递给函数 r，x 乘以 2。因此，x = 24。

**节目 2:**

```
a = 4.5
b = 2
print (a//b)
```

**输出:**

```
2.0
```

**说明:**这种除法称为[截断除法](https://www.geeksforgeeks.org/division-operator-in-python/)，余数被截断或丢弃。

**节目 3:**

```
a = True
b = False
c = False

if a or b and c:
    print ("GEEKSFORGEEKS")
else:
    print ("geeksforgeeks")
```

**输出:**

```
GEEKSFORGEEKS
```

**说明:**在 Python 中，AND 运算符的优先级高于 or 运算符。所以，先评估一下。即(b 和 c)评估为假。现在评估或运算符。这里，(真或假)的计算结果为真。所以 if 条件变为 True，GEEKSFORGEEKS 作为输出打印。

**节目 4:**

```
a = True
b = False
c = False

if not a or b:
    print (1)
elif not a or not b and c:
    print (2)
elif not a or b or not b and a:
    print (3)
else:
    print (4)
```

**输出:**

```
3

```

**解释:**在 Python 中，优先顺序是先非后与，最后或。因此，if 条件和第二个 elif 条件的计算结果为 False，而第三个 elif 条件的计算结果为 True，因此输出结果为 3。

**节目 5:**

```
count = 1 

def doThis():

    global count

    for i in (1, 2, 3): 
        count += 1

doThis()

print (count)
```

**输出:**

```
 4 
```

**说明:**函数外声明的变量计数是全局变量，函数中引用的计数变量也是函数外定义的同一个全局变量。因此，对函数中的变量所做的更改会反映到原始变量中。所以，程序的输出是 4。

[Python 小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。