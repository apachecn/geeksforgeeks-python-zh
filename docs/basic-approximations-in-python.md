# Python 中的基本近似

> 原文:[https://www . geesforgeks . org/basic-approximits-in-python/](https://www.geeksforgeeks.org/basic-approximations-in-python/)

近似是指估计不完全正确但几乎正确的东西的价值。它在科学技术领域发挥着至关重要的作用。让我们从最广为人知的例子开始。你用过圆周率的确切数值吗？当然不是。它是一个值很长的非终止无理数。如果我们继续写 *Pi* 的确切值，可能连这篇文章都不足以做到:

```py
3.14159 26535 89793 23846 26433 83279...
```

这就是近似值发挥作用的地方。我们通常将圆周率的值近似为 **`3.14`** 或者用有理数 **`22/7`** 来表示。当你升入高中时，你可能已经在数学中看到了更广泛的近似值的应用，它使用微分来近似量的值，如(36.6)^1/2 或(0.009) ^1/3.在计算机科学中，我们可以使用近似值来找到值，或者使用循环来近似某物的值。

**例如:**逼近任意数的立方根。看看下面的流程:

```py
# Python program to approximate 
# the cube root of 27
guess = 0.0
cube = 27
increment = 0.0001
epsilon = 0.1

# Finding the approximate value
while abs(guess**3 - cube) >= epsilon:
    guess+=increment

# Checking the approximate value
if abs(guess**3 - cube) >= epsilon:
    print("Failed on the cube root of",cube)
else:
    print(guess,"is close to the cube root of",cube) 
```

上述代码的输出为:

```py
2.9963000000018987 is close to the cube root of 27

```

我们可以看到，2.99 不是`(27)^1/3`的精确值，但是非常接近精确值 3。这就是我们所说的近似。这里我们使用了一系列的计算来近似这个值。首先我们声明一个变量`guess = 0.0`，我们将在一个循环中不断增加，直到它接近 27 的立方根。另一个变量`epsilon`选择得越少越好，以获得更准确的值。线路`while abs(guess**3 - cube) >= epsilon:`处理这个。如果它以大于`epsilon`的值退出循环，这意味着我们已经越过了近似值，并且测试失败。否则，它将返回猜测值。