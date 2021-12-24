# 利用 Cython 进行高性能阵列操作|第 2 集

> 原文:[https://www . geesforgeks . org/高性能-阵列-操作-with-cython-set-2/](https://www.geeksforgeeks.org/high-performance-array-operations-with-cython-set-2/)

先决条件:[使用 Cython 进行高性能阵列操作| Set 1](https://www.geeksforgeeks.org/high-performance-array-operations-with-cython-set-1/)
第一部分中的结果代码运行速度很快。在本文中，我们将比较代码与 NumPy 库中的 **clip()** 函数的性能。
令人惊讶的是，我们的程序比用 c 写的 NumPy 运行得更快。
**代码#1:性能比较。**

## 蟒蛇 3

```py
a = timeit('numpy.clip(arr2, -5, 5, arr3)',
       'from __main__ import b, c, numpy', number = 1000)

print ("\nTime for NumPy clip program : ", a)

b = timeit('sample.clip(arr2, -5, 5, arr3)',
           'from __main__ import b, c, sample', number = 1000)

print ("\nTime for our program : ", b)
```

**输出:**

```py
Time for NumPy clip program : 8.093049556000551

Time for our program :, 3.760528204000366
```

文章中的代码需要 ***Cython 键入的内存视图*** 来简化对数组进行操作的代码。声明 **cpdef clip()** 将 clip()声明为 C 级和 Python 级函数。这意味着其他 Cython 函数可以更有效地调用函数调用(例如，如果您想从不同的 Cython 函数调用 clip()。
代码中使用了两个装饰器–**@ cyt hon . boundcheck(False)**和**@ cyt hon . wrap(False)**。这是少数可选的性能优化。
**@ cyt hon . bounds check(False):**消除所有数组边界检查，如果索引不会超出范围，可以使用。
**@ cyt hon . wrapping(False):**消除了将负数组索引处理为绕到数组末尾(就像 Python 列表一样)。包含这些装饰器可以使代码运行得更快(在这个例子中测试时快了 2.5 倍)。
**代码#2:使用条件表达式**
的 clip()函数的变体

## 蟒蛇 3

```py
# decorators
@cython.boundscheck(False)
@cython.wraparound(False)

cpdef clip(double[:] a, double min, double max, double[:] out):

    if min > max:
        raise ValueError("min must be <= max")

    if a.shape[0] != out.shape[0]:
        raise ValueError
        ("input and output arrays must be the same size")

    for i in range(a.shape[0]):
        out[i] = (a[i]
        if a[i] < max else max)
        if a[i] > min else min
```

经过测试，这个版本的代码运行速度快了 50%以上。但是这些代码如何与手写的 C 语言版本相比较呢？经过实验，可以测试出手工制作的 C 扩展比 Cython 创建的版本运行速度慢 10%以上。