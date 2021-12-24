# Python 中的一级函数

> 原文:[https://www.geeksforgeeks.org/first-class-functions-python/](https://www.geeksforgeeks.org/first-class-functions-python/)

**一种语言中的第一类**对象被统一处理。它们可以存储在数据结构中，作为参数传递，或者用在控制结构中。如果一种编程语言将函数视为第一类对象，则称其支持第一类函数。Python 支持第一类函数的概念。

**一级函数的性质:**

*   函数是对象类型的一个实例。
*   您可以将函数存储在变量中。
*   您可以将函数作为参数传递给另一个函数。
*   您可以从函数返回函数。
*   您可以将它们存储在数据结构中，如哈希表、列表等

**Python 中第一类函数的示例**

**1。函数是对象:** Python 函数是一级对象。在下面的例子中，我们给一个变量赋值。这个赋值不调用函数。它接受 shout 引用的函数对象，并创建指向它的第二个名称，shout。

```py
# Python program to illustrate functions
# can be treated as objects
def shout(text):
    return text.upper()

print (shout('Hello'))

yell = shout

print (yell('Hello'))
```

**输出:**

```py
HELLO
HELLO

```

**2。函数可以作为参数传递给其他函数:**因为函数是对象，所以我们可以将它们作为参数传递给其他函数。可以接受其他函数作为参数的函数也称为高阶函数。在下面的例子中，我们创建了一个函数 **greet** ，它以一个函数作为参数。

```py
# Python program to illustrate functions
# can be passed as arguments to other functions
def shout(text):
    return text.upper()

def whisper(text):
    return text.lower()

def greet(func):
    # storing the function in a variable
    greeting = func("""Hi, I am created by a function
                    passed as an argument.""")
    print (greeting) 

greet(shout)
greet(whisper)
```

**输出**

```py
HI, I AM CREATED BY A FUNCTION PASSED AS AN ARGUMENT.
hi, i am created by a function passed as an argument.

```

**3。函数可以返回另一个函数:**因为函数是对象，所以我们可以从另一个函数返回一个函数。在下面的例子中，create_adder 函数返回加法器函数。

```py
# Python program to illustrate functions
# Functions can return another function

def create_adder(x):
    def adder(y):
        return x+y

    return adder

add_15 = create_adder(15)

print (add_15(10))
```

**输出:**

```py
25

```

本文由 **Mayank Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。