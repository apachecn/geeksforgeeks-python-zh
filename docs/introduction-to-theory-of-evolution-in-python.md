# Python 进化理论介绍

> 原文:[https://www . geeksforgeeks . org/python 进化理论简介/](https://www.geeksforgeeks.org/introduction-to-theory-of-evolution-in-python/)

遗传的过程包括特征以基因的形式从一代传递到另一代。这些基因实际上有脱氧核糖核酸，这是关于特征的编码信息。由于遗传，进化从一个物种发生到另一个物种。因此，我们可以得出结论，进化是一个随机的过程，因为它不会一蹴而就，而是需要数百万年才能发生。例如，从阿米巴原虫进化到人类，需要数百万年。

这个进化过程的随机性是可以模拟的。我们将以非常不同的方式模拟这个模型。实际上我们可以模拟和看到，进化是如何发生的。事实上，有一个‘T0’遗传算法的模型，它学习变形虫是如何进化成人类的。所以为了理解这个概念，这里我们不使用这个算法，因为对于初学者来说，理解起来会变得复杂得多。

为了理解进化的概念，我们将取一个非常大的二进制数，其中只包含零，然后我们将使用随机库将所有的零随机转换为一。你会震惊地发现，一段时间后，所有的 0 都会被转换成 1。
**将每个 0 转换为 1 所花费的时间将基于**

*   字符串的长度
*   我们将 0 转换为 1 的概率

下面是实现。假设进化过程需要 500 次。

```py
import random

def evolve(x):

    # index of the bit in x(list) 
    # in which change will happen
    i = random.randint(0, len(x)-1)

    # p is one then only change 
    # will happen
    p = random.randint(1, 5)
    if(p == 1):

        if(x[i] == 0):
            x[i] = 1

        else:
            x[i] = 1

# Driver code
x =[0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

# the process of evolution
# will take place 500 times
for j in range(0, 500):
    evolve(x)

print(x)
```

**输出:**

```py
[1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
```