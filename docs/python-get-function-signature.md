# Python–获取函数签名

> 原文:[https://www . geesforgeks . org/python-get-function-signature/](https://www.geeksforgeeks.org/python-get-function-signature/)

让我们考虑一个场景，其中您已经编写了非常长的代码，并且想要知道函数调用的细节。所以你可以做的是每次滚动你的代码，让不同的函数知道它们的细节，或者你可以聪明地工作。您可以创建一个代码，在其中您可以获得函数的详细信息，而无需滚动代码。这可以通过两种方式实现–

*   使用 signature()函数
*   使用装饰器

## 使用 signature()函数

我们可以借助 **signature()** 函数得到函数 Signature。它将可调用作为参数，并返回注释。如果未提供签名，它将引发错误值。如果给定了无效类型对象，那么它将引发类型错误。

**语法:**

```
inspect.signature(callable, *, follow_wrapped=True)
```

**例 1:**

```
from inspect import signature

# declare a function gfg with some
# parameter
def gfg(x:str, y:int):
    pass

# with the help of signature function
# store signature of the function in
# variable t
t = signature(gfg)

# print the signature of the function
print(t)

# print the annonation of the parameter
# of the function
print(t.parameters['x'])

# print the annonation of the parameter
# of the function
print(t.parameters['y'].annotation)
```

**输出**

```
(x:str, y:int)
x:str
<class 'int'>
```

## 使用装饰器

为此，Python 中的函数具有某些属性。其中一个属性是 __code__ 返回被调用的函数字节码。__code__ 属性也有一些属性可以帮助我们执行任务。我们将使用 co_varnames 属性和 co_argcount，前者返回参数和局部变量的名称元组，后者返回参数的数量(不包括仅包含关键字的参数，*或* * args)。让我们看看下面使用这些讨论的属性实现的装饰器。

**示例:**

```
# Decorator to print function call 
# details 
def function_details(func): 

    # Getting the argument names of the 
    # called function 
    argnames = func.__code__.co_varnames[:func.__code__.co_argcount] 

    # Getting the Function name of the 
    # called function 
    fname = func.__name__ 

    def inner_func(*args, **kwargs): 

        print(fname, "(", end = "") 

        # printing the function arguments 
        print(', '.join( '% s = % r' % entry 
            for entry in zip(argnames, args[:len(argnames)])), end = ", ") 

        # Printing the variable length Arguments 
        print("args =", list(args[len(argnames):]), end = ", ") 

        # Printing the variable length keyword 
        # arguments 
        print("kwargs =", kwargs, end = "") 
        print(")") 

    return inner_func 

# Driver Code 
@function_details
def GFG(a, b = 1, *args, **kwargs): 
    pass

GFG(1, 2, 3, 4, 5, d = 6, g = 12.9) 
GFG(1, 2, 3) 
GFG(1, 2, d = 'Geeks') 
```

**输出:**

> GFG (a = 1，b = 2，args = [3，4，5]，kwargs = { ' d ':' 6 '，g:12.9 })
> gfg(a = 1，b = 2，args = [3]，kwargs = {})
> GFG (a = 1，b = 2，args = [，kwargs = {'d': 'Geeks'})