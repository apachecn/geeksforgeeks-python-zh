# 如何统计 Python 中一个类的实例数？

> 原文:[https://www . geeksforgeeks . org/如何计算 python 中类的实例数/](https://www.geeksforgeeks.org/how-to-count-number-of-instances-of-a-class-in-python/)

类的实例是指为特定类创建的对象。一个类可以有多个对象。在这里，我们将找到 Python 中一个类的实例数。

**进场:**

*   每当创建对象时，都会调用该特定类的构造函数。
*   构造函数是一个名称与类名相同的函数，它没有任何返回类型。构造函数用于初始化类的变量。
*   每当一个构造函数被调用，这意味着一个新的对象被创建，我们只需要增加一个计数器，它将跟踪特定类的对象数量。

**下面是实现:**

## 蟒蛇 3

```py
# code
class geeks:

    # this is used to print the number
    # of instances of a class
    counter = 0

    # constructor of geeks class
    def __init__(self):

        # increment
        geeks.counter += 1

# object or instance of geeks class
g1 = geeks()
g2 = geeks()
g3 = geeks()
print(geeks.counter)
```

**输出:**

```py
3
```