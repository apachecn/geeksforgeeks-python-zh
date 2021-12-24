# 不使用 Python 中的任何循环打印 n 的前 m 倍

> 原文:[https://www . geesforgeks . org/print-first-m-n 的倍数而不使用 python 中的任何循环/](https://www.geeksforgeeks.org/print-first-m-multiples-of-n-without-using-any-loop-in-python/)

给定 n 和 m，不使用 Python 中的任何循环，打印 m 数的前 m 倍。

示例:

```py
Input : n = 2, m = 3
Output : 2 4 6 

Input : n = 3, m = 4
Output : 3 6 9 12 

```

我们可以使用 Python 中的 [range()函数](https://www.geeksforgeeks.org/range-vs-xrange-python/)来存储一个范围内的倍数。
首先使用 [range()](https://www.geeksforgeeks.org/range-vs-xrange-python/) 函数将数字存储到 m 的倍数，然后使用 **(*a)** 打印数组，不使用循环打印数组。

下面是上述方法的 Python 实现:

```py
# function to print the first m multiple
# of a number n without using loop.
def multiple(m, n):

    # inserts all elements from n to 
    # (m * n)+1 incremented by n.
    a = range(n, (m * n)+1, n)

    print(*a)

# driver code 
m = 4
n = 3
multiple(m, n)
```

**输出:**

```py
3 6 9 12

```

**注:**在 Python 3 中，`print(*(range(x))`相当于`print(" ".join([str(i) for i in range(x)]))`