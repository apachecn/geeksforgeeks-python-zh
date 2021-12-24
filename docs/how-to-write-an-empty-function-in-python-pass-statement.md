# 如何在 Python 中编写空函数–pass 语句？

> 原文:[https://www . geesforgeks . org/如何编写 python 中的空函数传递语句/](https://www.geeksforgeeks.org/how-to-write-an-empty-function-in-python-pass-statement/)

在 C/C++和 Java 中，我们可以编写如下的空函数

```
// An empty function in C/C++/Java
void fun() {  }

```

在 Python 中，如果我们用 Python 写类似下面这样的东西，会产生编译器错误。

```
# Incorrect empty function in Python
def fun(): 
```

输出:

```
IndentationError: expected an indented block
```

在 Python 中，为了编写空函数，我们使用**传递**语句。pass 是 Python 中的一个特殊语句，它不做任何事情。它只是作为一个伪语句工作。

```
# Correct way of writing empty function 
# in Python
def fun(): 
    pass
```

我们也可以在 while 语句中使用 pass。

```
# Empty loop in Python
mutex = True
while (mutex == True) :
    pass
```

我们可以在空 if else 语句中使用 pass。

```
# Empty in if/else in Python
mutex = True
if (mutex == True) :
    pass
else :
    print("False")
```

本文由**希瓦姆·古普塔**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论