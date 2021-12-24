# Python 中的全局和局部变量

> 原文:[https://www . geesforgeks . org/global-local-variables-python/](https://www.geeksforgeeks.org/global-local-variables-python/)

**全局变量**是那些没有在任何函数中定义并且具有全局范围的变量，而**局部变量**是那些在函数中定义并且其范围仅限于该函数的变量。换句话说，我们可以说局部变量只能在初始化它的函数内部访问，而全局变量可以在整个程序和每个函数内部访问。

## 局部变量

局部变量是那些在函数内部初始化的变量，并且只属于那个特定的函数。它不能在函数之外的任何地方访问。让我们看看如何创建一个局部变量。

**示例:**创建局部变量

## 蟒蛇 3

```
def f():

    # local variable
    s = "I love Geeksforgeeks"
    print(s)

# Driver code
f()
```

**Output**

```
I love Geeksforgeeks
```

如果我们试图在函数外使用这个局部变量，那么让我们看看会发生什么。

**示例:**

## 蟒蛇 3

```
def f():

    # local variable
    s = "I love Geeksforgeeks"
    print("Inside Function:", s)

# Driver code
f()
print(s)
```

**输出**

```
NameError: name 's' is not defined
```

## 全局变量

全局变量是在任何函数之外定义的变量，并且可以在整个程序中访问，即在每个函数的内部和外部。让我们看看如何创建一个全局变量。

**示例:**定义和访问全局变量

## 蟒蛇 3

```
# This function uses global variable s
def f():
    print("Inside Function", s)

# Global scope
s = "I love Geeksforgeeks"
f()
print("Outside Function", s)
```

**Output**

```
Inside Function I love Geeksforgeeks
Outside Function I love Geeksforgeeks
```

变量 s 被定义为全局变量，在函数内部和函数外部都使用。

**注意:**由于没有局部变量，将使用全局变量的值。

现在，如果有一个同名的变量在一个函数中被全局初始化了呢？现在问题来了，局部变量会不会对全局变量有一些影响，反之亦然，如果我们改变函数 f()内部变量的值会怎么样？它也会影响全球吗？我们在下面的代码中测试它:

## 蟒蛇 3

```
# This function has a variable with
# name same as s.
def f():
    s = "Me too."
    print(s)

# Global scope
s = "I love Geeksforgeeks"
f()
print(s)
```

**输出:**

```
Me too.
I love Geeksforgeeks.
```

如果在函数的作用域内也定义了一个同名的变量，那么它将只打印函数内部给出的值，而不是全局值。

问题是，如果我们试图改变函数内部的全局变量的值会怎么样。让我们用下面的例子来看看。

**示例:**

## 蟒蛇 3

```
# This function uses global variable s
def f():
    s += 'GFG'
    print("Inside Function", s)

# Global scope
s = "I love Geeksforgeeks"
f()
```

**输出**

```
UnboundLocalError: local variable 's' referenced before assignment
```

要使上述程序工作，我们需要使用“global”关键字。让我们看看这个全局关键词是什么。

## 全局关键字

如果我们想做赋值或者改变全局变量，我们只需要在函数中使用**全局关键字**。打印和访问不需要全局。Python“假设”我们想要一个局部变量，因为在 f()内部赋值给 s，所以第一条语句抛出错误消息。任何在函数内部更改或创建的变量，如果没有声明为全局变量，都是局部变量。要告诉 Python，我们想要使用全局变量，我们必须使用关键字**“全局”**，如下例所示:

**示例 1:** 使用全局关键字

## 蟒蛇 3

```
# This function modifies the global variable 's'
def f():
    global s
    s += ' GFG'
    print(s)
    s = "Look for Geeksforgeeks Python Section"
    print(s)

# Global Scope
s = "Python is great!"
f()
print(s)
```

**Output**

```
Python is great! GFG
Look for Geeksforgeeks Python Section
Look for Geeksforgeeks Python Section
```

现在没有歧义了。

**示例 2:** 使用全局和局部变量

## 蟒蛇 3

```
a = 1

# Uses global because there is no local 'a'
def f():
    print('Inside f() : ', a)

# Variable 'a' is redefined as a local
def g():
    a = 2
    print('Inside g() : ', a)

# Uses global keyword to modify global 'a'
def h():
    global a
    a = 3
    print('Inside h() : ', a)

# Global scope
print('global : ', a)
f()
print('global : ', a)
g()
print('global : ', a)
h()
print('global : ', a)
```

**Output**

```
global :  1
Inside f() :  1
global :  1
Inside g() :  2
global :  1
Inside h() :  3
global :  3
```

本文由 **Shwetanshu Rohatgi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。