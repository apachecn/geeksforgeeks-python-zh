# 改变你在代码中加入逻辑的方式——Python

> 原文:[https://www . geesforgeks . org/change-your-way-to-put-logic-in-your-code/](https://www.geeksforgeeks.org/change-your-way-to-put-logic-in-your-code/)

这些年来，你不厌倦用同样的传统逻辑编码吗？是时候带来一些不同了。不管是什么编程语言。当我们被要求做一些基本的编程练习，如排序、搜索、质数检查等。我们都被推向同一条船，这是相同的编码逻辑。现在，我们已经过去了 2020 年，所以在编码方面，我们也要主动改变我们的思维方式。这是因为，只有我们用不同的方式思考，我们才能用不同的方式编码。

让我们深入探讨这些精彩的编码技巧。

## 检查给定的数字是奇数还是偶数

当然，多么简单的问题。我们可以使用**模数运算符轻松检查偶数或奇数。**你想知道怎么做？只需查看下面的 Python 代码片段–

## 蟒蛇 3

```
a = 4

if(a % 2 == 0):
    print("even")
else:
    print("odd")
```

**输出:**

```
even

```

这里，模数运算用于确定所获得的余数。所有偶数都可以被 2 整除。这意味着，将一个偶数比如 4 除以 2，我们将得到余数为 0。所以在这两个数字之间应用模运算，答案是 0。每当我们被要求检查奇数和偶数时，这个基本原则总是适用于编程。

你能有不同的想法吗？我们都教会了大脑这样一个逻辑:一个数除以 2 决定了它是奇数还是偶数。这一行代码传统上由所有编写代码的人遵循。所以让我们开始挖掘一种常青树，但没有使用的方法。

T2T4

```
a = 4

if(a & 1):
    print("odd")
else:
    print("even")
```

T5

**输出:**

```
even

```

这是使用**逐位“与”运算**完成的。够酷了！

按位运算符一点一点地对整数进行运算。这是通过将整数转换为二进制，然后对每个相应的位执行逻辑与运算来实现的。

**注意:**更多信息请参考 [Python 按位运算符](www.geeksforgeeks.org/python-bitwise-operators/)

## 检查给定的数是否是质数？

那些只能被 1 整除的数叫做**质数**。素数的例子有 2、3、5、7 等。其中没有任何其他因素(不包括自身和 1)。我们都学过以下检查素数的逻辑。

## 蟒蛇 3

```
a = 10

if a>1:

    for i in range(2, (a//2)+1):

        if a % i == 0:
            print(a, "is not prime ")
            break

        else:
            print(a, "is prime ")
else:
    print(a, "is not prime ")
```

**输出:**

```
10 is not prime 

```

但是我们可以更优化它。而且看起来会像:

## 蟒 3

```
a = 10
i = 2

if a>1:

    while(i * i<a):

        if a % i == 0:
            print(a, "is not prime ")
            break

        else:
            print(a, "is prime ")
        i += 1
else:
    print(a, "is not prime ")
```

**输出:**

```
10 is not prime 

```

两个代码都是正确的，并输出相同的结果。但是第二个代码更优化，因为要检查因子，循环到给定数字的平方根就足够了，而不是检查到它的一半。

在上面的代码中，我们正在检查给定数字的因子。每次迭代后，我们必须增加循环变量“I”的值。它的功能直到 i^2 少于给定的数字。

## 将给定的数字 k 乘以 2^k 并显示输出

这可以通过基本的数学步骤用任何语言轻松编码。所以步骤是:

*   Assign a value, for example, 5 to a variable' k'
*   Then, we will store the value of 2.5 in another variable J.
*   In , multiply the contents of k and j by
*   Display output. (Here 160 will be the result output)

这可以用几行代码来编码，代码如下:

## 蟒 3

```
k = 5
j = 2**k
p = k * j

print(p)
```

**输出:**

```
160
```

但是还有一种方法更简单有效。也就是通过使用**移位运算符。**对变量 k 进行左移操作，k 次将产生与上面显示的相同的功能。因此优化后的代码将变成:

## 蟒蛇 3

```
k = 5

print(k<<k)
```

**输出:**

```
160
```

这两者将导致相同的输出。

## 用给定的数字除以 2^k 并显示输出

除法函数的工作原理也类似于乘法函数。只有操作员会改变。下面列出了用 2^k 除一个数的步骤:

*   Assign a value, for example, 5 to a variable' k'
*   Then, we will store the value of 2.5 in another variable J.
*   Divide the contents of K and J.
*   Display output. (Here 160 will be the result output)

基本划分的 Python 3 代码如下:

## Python 3

```
k = 5
j = 2**k

p = k//j

print(p)
```

**输出:**

```
0
```

根据我们的要求，我们可以使用“//”进行整数划分，使用“/”进行楼层划分。而优化后的代码使用右移操作会看起来像:

## python 3

T0T6】

**输出:**

```
0
```

这两个代码将导致输出“0”(整数除法)。

**注意:**更多信息请参考 [Python 按位运算符。](https://www.geeksforgeeks.org/python-bitwise-operators/)

所有这些操作从历史上就已经存在了。但是我们忘了练习使用它们。为了我们不断变化的未来，让我们采纳这些小小的改变，成为其中的一部分。