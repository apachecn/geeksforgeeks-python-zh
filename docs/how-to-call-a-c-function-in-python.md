# 如何在 Python 中调用 C 函数

> 原文:[https://www . geesforgeks . org/如何调用 python 中的 a-c-function/](https://www.geeksforgeeks.org/how-to-call-a-c-function-in-python/)

你有没有遇到过必须用 python 调用 C 函数的情况？这篇文章将在一个非常基本的层面上帮助你，如果你没有遇到过这样的情况，你会喜欢知道这是如何可能的。
首先，我们用 C 写一个简单的函数，生成文件的共享库。假设文件名是 function.c。

## C

```py
int myFunction(int num)
{
    if (num == 0)

        // if number is 0, do not perform any operation.
        return 0;
    else
        // if number is power of 2, return 1 else return 0
          return ((num & (num - 1)) == 0 ? 1 : 0) ;

}
```

编译这个:

```py
cc -fPIC -shared -o libfun.so function.c
```

### **使用 ctypes(外部函数接口)库从 Python 中调用 C 函数**

上面的语句将生成一个名为 libfun.so 的共享库。现在，让我们看看如何在 python 中使用它。在 python 中，我们有一个名为 ctypes 的库。利用这个库，我们可以在 python 中使用 C 函数。
假设文件名为 function.py.

## 蟒蛇 3

```py
import ctypes
NUM = 16     
# libfun loaded to the python file
# using fun.myFunction(),
# C function can be accessed
# but type of argument is the problem.

fun = ctypes.CDLL("libfun.so") # Or full path to file 
# Now whenever argument
# will be passed to the function                                                       
# ctypes will check it.

fun.myFunction.argtypes = [ctypes.c_int]

# now we can call this
# function using instant (fun)
# returnValue is the value
# return by function written in C
# code
returnVale = fun.myFunction(NUM)       
```