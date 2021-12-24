# Python 中的 Currying 函数

> 原文:[https://www.geeksforgeeks.org/currying-function-in-python/](https://www.geeksforgeeks.org/currying-function-in-python/)

在问题解决和函数式编程中，*curry*是一种简化函数执行的做法，该函数将多个参数转换为执行连续的单参数函数。简单来说，Currying 是通过评估函数参数的增量嵌套，将多参数函数转化为单参数函数。Currying 还会在执行时将一个参数修正为另一个参数，从而形成相对模式。

**Currying 的数学图示:**
一般来说，函数 Currying 占用任意数量的计算和数据来生成一个返回预期输出的实函数。我们开始吧，

```
f(x, y) = (x*x*x) + (y*y*y)
h(x) = (x*x*x)
h(y) = (y*y*y)
h(x)(y) = h(x)+h(y)
f(x, y) = h(x)(y)
Curry f = h(x)(y)
```

例如，我们将把函数的组成链接起来。

**a(x) = b(c(d(x)))**

```
def change(b, c, d):
    def a(x):
        return b(c(d(x)))
    return a
```

**v(a、b、c、d、e) = w(x(y(z(a、b、c、d、e))))**

```
# Currying in Python - Many to Single Argument
 def change(a):
    def w(b):
        def x(c):
            def y(d):
                def z(e):
                    print(a, b, c, d, e)
                return z
            return y
        return x
    return w

change(10)(20)(30)(40)(50)
```

**输出:**

```
10 20 30 40 50
```

这里，概念是将一个函数嵌套到另一个函数中，因此一个函数的结果被记录在函数链中。通过将一个巨大的操作块简化为更简单的顺序块。

**代码#1:** 公里改米，米改厘米。

```
# Demonstrate Currying of composition of function
def change(b, c, d):
    def a(x):
        return b(c(d(x)))
    return a

def kilometer2meter(dist): 
    """ Function that converts km to m. """
    return dist * 1000

def meter2centimeter(dist): 
    """ Function that converts m to cm. """
    return dist * 100

def centimeter2feet(dist):
    """ Function that converts cm to ft. """
    return dist / 30.48

if __name__ == '__main__':
    transform = change(centimeter2feet, meter2centimeter, kilometer2meter )
    e = transform(565)
    print(e)

```

**输出:**

```
1853674.5406824148
```

**代码#2:**

```
# Demonstrate Currying of composition of function

def change(b, c, d):
    def a(x):
        return b(c(d(x)))
    return a

def daystohour(time): 
    """ Function that converts days to hours. """
    return time * 24

def hourstominutes(time): 
    """ Function that converts hours to minutes. """
    return time * 60

def minutestoseconds(time):
    """ Function that converts minutes to seconds. """
    return time * 60

if __name__ == '__main__':
    transform = change(minutestoseconds, hourstominutes, daystohour)
    e = transform(10)
    print(e)

```

**输出:**

```
864000
```