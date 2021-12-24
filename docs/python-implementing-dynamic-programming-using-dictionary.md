# Python |使用字典实现动态编程

> 原文:[https://www . geesforgeks . org/python-实现-动态-编程-使用-字典/](https://www.geeksforgeeks.org/python-implementing-dynamic-programming-using-dictionary/)

[动态规划](https://www.geeksforgeeks.org/dynamic-programming/)是一种可以作为对普通[递归](https://www.geeksforgeeks.org/recursion/)的优化的方法。无论我们在哪里看到对相同输入重复调用的递归解决方案，我们都可以使用动态编程对其进行优化。这个想法是简单地存储子问题的结果，这样我们就不必在以后需要时重新计算它们。这种简单的优化减少了从指数到多项式的时间复杂性。本文讨论了一种利用 python 的[字典](https://www.geeksforgeeks.org/python-dictionary/)实现动态编程的方法。

为了理解 python 中动态编程的实现，让我们使用[斐波那契数](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)问题来可视化它。

在数学术语中，斐波那契数列由递归关系定义:

```py
Fn = Fn-1 + Fn-2
```

带有种子值:

```py
F0 = 0 and F1 = 1
```

**示例:**

> **输入:** N = 9
> **输出:** 34
> **解释:**
> 9 <sup>斐波那契数列中的第</sup>数为 34。
> 
> **输入:** N = 2
> **输出:** 1
> **说明:**
> 2 <sup>nd</sup> 斐波那契数列中的数字为 1。

下面是天真方法的实现:

## 蟒蛇 3

```py
# Function to find nth Fibonacci number
def Fibonacci(n):

    # Corner case
    if n<0:
        print("Incorrect input")

    # Base case
    elif n == 0:
        return 0
    elif n == 1:
        return 1

    # Recursive case
    else:
        return Fibonacci(n-1)+Fibonacci(n-2)

print(Fibonacci(9))
```

**Output:** 

```py
34
```

显然，上述方法具有指数级的时间复杂度。为了存储之前计算的结果，让我们使用 python 的[字典](https://www.geeksforgeeks.org/python-dictionary/)类。

**方法:**思路是自定义字典类的 *__missing__* 方法。当用户试图访问不在字典中的键时，将执行此方法。我们将使用我们自己的函数定义来重写这个方法。
以下是上述办法的实施情况:

## 蟒蛇 3

```py
# Python program to customize the
# __missing__ method of the
# dictionary class in python

class Fibonacci(dict):

    # Function signature of the
    # __missing__ function in
    # python
    def __missing__(self, n):

        # Base case
        if n<= 1:

            # Storing the value in the
            # dictionary before returning
            self[n] = n
            return n

        # Storing the value in the dictionary
        # before returning the value
        val = self[n] = self[n-1] + self[n-2]
        return val

if __name__ == "__main__":

    # Create an instance of the class
    Fib = Fibonacci()
    N = Fib[9]
    print(N)
```

**Output:** 

```py
34
```

上述方法也可以用 python 中的[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)来实现。
[Decorator](https://www.geeksforgeeks.org/function-decorators-in-python-set-1-introduction/) 是 python 中非常强大和有用的工具，因为它允许程序员修改函数或类的行为。装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。这里，[记忆](https://www.geeksforgeeks.org/memoization-using-decorators-in-python/?ref=rp)用于实现装饰器。

下面是上述方法的实现:

## 蟒蛇 3

```py
# Python program to find the nth Fibonacci
# number with memoization using decorators

from inspect import signature

# Defining a decorator
class memoize(dict):

    # Initializing function
    def __init__(self, func):
        self.func = func
        self.signature = signature(func)

    # Missing method to store the
    # Fibonacci numbers in a
    # Dictionary
    def __missing__(self, key):
        (arg, kwarg) = key
        self[key] = val = self.func(*arg, 
                          **dict(kwarg))
        return val

    def __call__(self, *arg, **kwarg):
        key = self.signature.bind(*arg,
                                  **kwarg)
        return self[key.args,
                    frozenset(key.kwargs.items())]

# Function to find the n-th Fibonacci
# number using the above defined
# decorator
@memoize
def Fibonacci(n):

    # Corner case
    if n<0:
        print("Incorrect input")

    # Base cases
    elif n == 0:
        return 0
    elif n == 1:
        return 1

    # Recursive case
    else:
        return Fibonacci(n-1)+Fibonacci(n-2)

if __name__ == "__main__":
    print(Fibonacci(9))
```

**Output:** 

```py
34
```