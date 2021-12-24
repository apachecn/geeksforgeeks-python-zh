# Python 中的生成器

> 原文:[https://www.geeksforgeeks.org/generators-in-python/](https://www.geeksforgeeks.org/generators-in-python/)

先决条件:[产生关键字](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/)和[迭代器](https://www.geeksforgeeks.org/iterators-in-python/)

当我们讨论发电机时，涉及两个术语。

1.  **Generator-Function :** A generator-function is defined like a normal function, but whenever it needs to generate a value, it does so with the [yield keyword](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/) rather than return. If the body of a def contains yield, the function automatically becomes a generator function.

    ```
    # A generator function that yields 1 for first time,
    # 2 second time and 3 third time
    def simpleGeneratorFun():
        yield 1            
        yield 2            
        yield 3            

    # Driver code to check above generator function
    for value in simpleGeneratorFun(): 
        print(value)
    ```

    输出:

    ```
    1
    2
    3
    ```

2.  **Generator-Object :** Generator functions return a generator object. Generator objects are used either by calling the next method on the generator object or using the generator object in a “for in” loop (as shown in the above program).

    ```
    # A Python program to demonstrate use of 
    # generator object with next() 

    # A generator function
    def simpleGeneratorFun():
        yield 1
        yield 2
        yield 3

    # x is a generator object
    x = simpleGeneratorFun()

    # Iterating over the generator object using next
    print(x.next()) # In Python 3, __next__()
    print(x.next())
    print(x.next())
    ```

    输出:

    ```
    1
    2
    3
    ```

因此，生成器函数返回一个可迭代的生成器对象，即可以用作[迭代器](https://www.geeksforgeeks.org/iterators-in-python/)。

作为另一个例子，下面是斐波那契数的生成器。

```
# A simple generator for Fibonacci Numbers
def fib(limit):

    # Initialize first two Fibonacci Numbers 
    a, b = 0, 1

    # One by one yield next Fibonacci Number
    while a < limit:
        yield a
        a, b = b, a + b

# Create a generator object
x = fib(5)

# Iterating over the generator object using next
print(x.next()) # In Python 3, __next__()
print(x.next())
print(x.next())
print(x.next())
print(x.next())

# Iterating over the generator object using for
# in loop.
print("\nUsing for in loop")
for i in fib(5): 
    print(i)
```

输出:

```
0
1
1
2
3

Using for in loop
0
1
1
2
3
```

**应用:**假设我们要创建一个斐波那契数列，采用生成器的方法使它变得微不足道；我们只需要调用 next(x)就可以得到下一个斐波那契数，而不用担心数字流在哪里或什么时候结束。
一种更实用的流处理类型是处理大型数据文件，如日志文件。生成器为这种数据处理提供了一种节省空间的方法，因为在一个给定的时间点只处理文件的一部分。我们也可以使用迭代器来实现这些目的，但是生成器提供了一种快速的方法(我们不需要在这里编写 __next__ 和 __iter__ 方法)。

关于 Python 中生成器的更高级应用，请参考下面的链接。
[http://www.dabeaz.com/finalgenerator/](http://www.dabeaz.com/finalgenerator/)

本文由 **Shwetanshu Rohatgi** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论