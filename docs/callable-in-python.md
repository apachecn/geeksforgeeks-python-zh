# Python 中的可调用()

> 原文:[https://www.geeksforgeeks.org/callable-in-python/](https://www.geeksforgeeks.org/callable-in-python/)

一般来说，可调用是可以调用的东西。Python 中的这个内置方法检查并返回 True，如果传递的对象看起来是可调用的，但可能不是，否则返回 False。
<font size="">**语法:**</font>

```py
callable(object)
```

callable()方法只接受一个参数和一个对象，并返回两个值之一:

*   如果对象看起来是可调用的，则返回 True。
*   如果对象不可调用，则返回 False。

**注意:**可能很少有 callable()返回 true，但对对象的调用失败的情况。但是如果一个 case 返回 False，调用对象将永远不会成功。

**情况:当对象可调用时**

```py
# Python program to illustrate 
# callable()
# a test function
def Geek():
    return 5

# an object is created of Geek()
let = Geek
print(callable(let))

# a test variable
num = 5 * 5
print(callable(num))
```

输出:

```py
True
False

```

**说明:**

*   这里，我们看到在第一种情况下，当一个对象在 callable()方法中传递时，它返回 True。之所以如此，是因为 *let* 是可调用函数 *Geek* 的对象(可能不是所有情况下都是)。
*   第二种情况 *num* 绝对不是可调用对象，所以结果为 False。

内置的 callable()方法检查参数是否为以下两种情况之一:

*   具有*_ _ 调用 __* 方法的类的实例。
*   属于具有的类型，该类型指示可调用性，例如在函数、方法等中。或者具有非空的 tp_call (c 结构)成员

示例:

```py
# Python program to illustrate 
# callable()
class Geek:
    def __call__(self):
        print('Hello GeeksforGeeks')

# Suggests that the Geek class is callable
print(callable(Geek))

# This proves that class is callable
GeekObject = Geek()
GeekObject()
```

输出:

```py
True
Hello GeeksforGeeks

```

**说明:**由于第一种情况返回并打印 True，说明 Geek 类可能是可调用的。接下来，我们能够调用 *__call__* 方法，并且它是可访问的，从而证明该类是可调用的。

**情况:当对象不可调用时**

让我们看看这个例子会发生什么:

```py
# Python program to illustrate 
# callable()
class Geek:
  def testFunc(self):
    print('Hello GeeksforGeeks')

# Suggests that the Geek class is callable
print(callable(Geek))

GeekObject = Geek()
# The object will be created but 
# returns an error on calling
GeekObject()
```

输出:

```py
True

```

**解释:**callable()方法返回 True，提示 Geek 类是可调用的，但是 Geek 的实例是不可调用的()，它返回一个运行时错误:

```py
Traceback (most recent call last):
  File "/home/3979dc83032f2d29befe45b6ee6001a4.py", line 10, in 
    GeekObject()
TypeError: 'Geek' object is not callable

```

本文由 [**【钦莫伊蕾恩卡】**](https://www.linkedin.com/in/lenkachinmoy/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。