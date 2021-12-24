# Python 中使用装饰器的记忆

> 原文:[https://www . geeksforgeeks . org/memo ization-use-decorator-in-python/](https://www.geeksforgeeks.org/memoization-using-decorators-in-python/)

递归是一种编程技术，其中函数重复调用自己，直到满足终止条件。使用递归的一些例子有:计算[斐波那契](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)级数，阶乘等。但是他们的问题是，在递归树中，已经解决的子问题可能会再次被解决，这增加了开销。

[记忆](https://www.geeksforgeeks.org/memoization-1d-2d-and-3d/)是一种记录中间结果的技术，这样可以避免重复计算，加快程序速度。它可以用来优化使用递归的程序。在 Python 中，记忆可以在函数装饰器的帮助下完成。

让我们以计算一个数的阶乘为例。下面的简单程序使用递归来解决这个问题:

```
# Simple recursive program to find factorial
def facto(num):
    if num == 1:
        return 1
    else:
        return num * facto(num-1)

print(facto(5))
```

以上程序可以使用[装饰器](https://www.geeksforgeeks.org/function-decorators-in-python-set-1-introduction/)进行记忆优化。

```
# Factorial program with memoization using
# decorators.

# A decorator function for function 'f' passed
# as parameter
def memoize_factorial(f):
    memory = {}

    # This inner function has access to memory
    # and 'f'
    def inner(num):
        if num not in memory:         
            memory[num] = f(num)
        return memory[num]

    return inner

@memoize_factorial
def facto(num):
    if num == 1:
        return 1
    else:
        return num * facto(num-1)

print(facto(5))
```

说明:
1。已经定义了一个名为 *memoize_factoria* l 的函数。它的主要目的是将中间结果存储在名为 memory 的变量中。
2。第二个函数叫做*事实上*是计算阶乘的函数。它已经被装饰器(函数 memoize _ 阶乘)注释了。由于闭包的概念，*事实上*可以访问*内存*变量。注释相当于写作，

```
facto = memoize_factorial(facto)

```

3.当调用 factor(5)时，除了存储中间结果之外，还会进行递归操作。每次需要进行计算时，都会检查结果是否存在于*存储器*中。如果是，则使用，否则，计算值并存储在*存储器*中。
4。我们可以验证记忆确实有效，请看[这个](https://ide.geeksforgeeks.org/5DjCwox4B9)程序的输出。