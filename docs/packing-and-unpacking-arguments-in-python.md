# Python 中的打包和解包参数

> 原文:[https://www . geesforgeks . org/packing-and-unpacking-arguments-in-python/](https://www.geeksforgeeks.org/packing-and-unpacking-arguments-in-python/)

我们使用两个运算符*(对于元组)和**(对于字典)。

**背景**
考虑一种情况，我们有一个接收四个参数的函数。我们想调用这个函数，我们有一个大小为 4 的列表，其中包含了函数的所有参数。如果我们简单地将一个列表传递给函数，调用就不起作用了。

## 计算机编程语言

```py
# A Python program to demonstrate need
# of packing and unpacking

# A sample function that takes 4 arguments
# and prints them.
def fun(a, b, c, d):
    print(a, b, c, d)

# Driver Code
my_list = [1, 2, 3, 4]

# This doesn't work
fun(my_list)
```

**输出:**

```py
TypeError: fun() takes exactly 4 arguments (1 given)
```

**解包**
我们可以使用 ***** 来解包列表，这样它的所有元素都可以作为不同的参数传递。

## 计算机编程语言

```py
# A sample function that takes 4 arguments
# and prints the,
def fun(a, b, c, d):
    print(a, b, c, d)

# Driver Code
my_list = [1, 2, 3, 4]

# Unpacking list into four arguments
fun(*my_list)
```

**输出:**

```py
(1, 2, 3, 4)
```

我们需要记住，参数的数量必须与我们为参数打开的列表长度相同。

## 蟒蛇 3

```py
# Error when len(args) != no of actual arguments
# required by the funcntion

args = [0, 1, 4, 9]

def func(a, b, c):
    return a + b + c

# calling function with unpacking args
func(*args)
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/592a8d2a568a0c12061950aa99d6dec3.py", line 10, in <module>
    func(*args)
TypeError: func() takes 3 positional arguments but 4 were given
```

作为另一个例子，考虑内置的 range()函数，它需要单独的 start 和 stops 参数。如果它们不能单独使用，用*-运算符编写函数调用，从列表或元组中解包参数:

## 计算机编程语言

```py
>>>
>>> range(3, 6)  # normal call with separate arguments
[3, 4, 5]
>>> args = [3, 6]
>>> range(*args)  # call with arguments unpacked from a list
[3, 4, 5]
```

**打包**
当我们不知道一个 python 函数需要传递多少个参数时，我们可以使用 Packing 将所有参数打包到一个元组中。

## 计算机编程语言

```py
# A Python program to demonstrate use
# of packing

# This function uses packing to sum
# unknown number of arguments
def mySum(*args):
    return sum(args)

# Driver code
print(mySum(1, 2, 3, 4, 5))
print(mySum(10, 20))
```

**输出:**

```py
15
30
```

上面的函数 mySum()进行“打包”，将此方法调用接收的所有参数打包到一个变量中。一旦我们有了这个“打包”的变量，我们就可以像使用普通元组一样使用它。args[0]和 args[1]将分别给出第一个和第二个参数。因为我们的元组是不可变的，所以您可以将 args 元组转换为列表，这样您也可以在 i.
中修改、删除和重新排列项目

**包装和拆箱**
下面是一个展示包装和拆箱的例子。

## 计算机编程语言

```py
# A Python program to demonstrate both packing and
# unpacking.

# A sample python function that takes three arguments
# and prints them
def fun1(a, b, c):
    print(a, b, c)

# Another sample function.
# This is an example of PACKING. All arguments passed
# to fun2 are packed into tuple *args.
def fun2(*args):

    # Convert args tuple to a list so we can modify it
    args = list(args)

    # Modifying args
    args[0] = 'Geeksforgeeks'
    args[1] = 'awesome'

    # UNPACKING args and calling fun1()
    fun1(*args)

# Driver code
fun2('Hello', 'beautiful', 'world!')
```

**输出:**

```py
(Geeksforgeeks, awesome, world!)
```

****用于词典**

## 计算机编程语言

```py
# A sample program to demonstrate unpacking of
# dictionary items using **
def fun(a, b, c):
    print(a, b, c)

# A call with unpacking of dictionary
d = {'a':2, 'b':4, 'c':10}
fun(**d)
```

**输出:**

```py
2 4 10
```

这里**解包了与之一起使用的字典，并将字典中的项目作为关键字参数传递给函数。所以写“好玩(1，**d)”就相当于写“好玩(1，b=4，c=10)”。

## 计算机编程语言

```py
# A Python program to demonstrate packing of
# dictionary items using **
def fun(**kwargs):

    # kwargs is a dict
    print(type(kwargs))

    # Printing dictionary items
    for key in kwargs:
        print("%s = %s" % (key, kwargs[key]))

# Driver code
fun(name="geeks", ID="101", language="Python")
```

**输出:**

```py
<class 'dict'>
language = Python
name = geeks
ID = 101
```

应用和要点

1.  在套接字编程中用于向服务器发送大量请求。
2.  在 Django 框架中用于发送变量参数来查看函数。
3.  有一些包装函数需要我们传入变量参数。
4.  修改参数变得很容易，但同时验证是不恰当的，因此必须小心使用。

**参考:**
[http://hangear . runway 7 . net/python/packing-拆包-arguments](http://hangar.runway7.net/python/packing-unpacking-arguments)
本文由 **Shwetanshu Rohatgi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息