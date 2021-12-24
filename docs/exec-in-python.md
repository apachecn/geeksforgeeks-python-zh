# Python 中的 exec()

> 原文:[https://www.geeksforgeeks.org/exec-in-python/](https://www.geeksforgeeks.org/exec-in-python/)

**exec()** 函数用于 Python 程序的动态执行，可以是字符串，也可以是目标代码。如果它是一个字符串，则该字符串被解析为一组 Python 语句，然后执行这些语句，除非出现语法错误；如果它是一个目标代码，则简单地执行它。我们必须小心，返回语句不能在函数定义之外使用，甚至不能在传递给 exec()函数的代码上下文中使用。它不返回任何值，因此返回*无*。

**语法:**

```py
exec(object[, globals[, locals]])
```

它可以采用三个参数:

*   **对象:**如前所述，这可以是字符串或对象代码
*   **全局:**可以是字典，参数可选
*   **局部变量:**这可以是一个映射对象，也是可选的

现在让我们看看这个函数是如何工作的。在下面的代码中，我们使用了一个目标代码，并使用 exec()函数执行了它。我们刚刚获取了对象参数，省略了另外两个字段。

示例:

## 蟒蛇 3

```py
prog = 'print("The sum of 5 and 10 is", (5+10))'
exec(prog)
```

输出:
5 和 10 的和是 15

**警告或限制**

在 exec()函数中使用任何方法之前，必须记住 exec()支持的所有函数。要查看这一点，我们可以使用 dir()函数。

示例:

## 蟒蛇 3

```py
# The math class is used to include all the
# math functions
from math import *
exec("print(dir())")
```

输出:

```py
['__builtins__', '__cached__', '__doc__', '__file__',
 '__loader__', '__name__', '__package__', '__spec__', 
'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 
'atanh', 'ceil', 'copysign', 'cos', 'cosh', 'degrees', 
'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial',
 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 
'hypot', 'inf', 'isclose', 'isfinite', 'isinf',
'isnan', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 
'log2', 'modf', 'nan', 'pi', 'pow', 'radians', 'sin',
 'sinh', 'sqrt', 'tan', 'tanh', 'trunc']
```

**全局和局部参数**

Python 允许我们通过使用可能不需要的全局和局部参数来限制各种变量和方法的使用。这些局部和全局参数主要用于局部或全局变量字典。如果缺少局部参数，全局参数将取代，这意味着全局参数可用于两个字段。让我们看看代码如何只传递全局参数。

示例:

## 蟒蛇 3

```py
# Here we have passed an empty dictionary
from math import *
exec("print(dir())", {})
```

输出:

```py
['__builtins__']
```

所以我们看到，在传递一个空字典作为全局参数时，只显示 _ _ builtins _ _ 而不显示其他数学函数，就像前面的例子一样。这意味着对象参数将只支持 _ _ builtins _ _ 参数。这表明所有其他功能都被限制在对象上。为了证明这一点，让我们试着用一个数学函数，看看会发生什么。

示例:

## 蟒蛇 3

```py
# An exception will be raised
from math import *
exec("print(factorial(5))", {})
```

输出:

```py
No Output
```

本示例应该打印 120 作为输出，但是它显示“无输出”并引发异常。虽然我们已经导入了数学模块，但是由于我们通过传递全局参数设置的限制，阶乘()方法无法工作。
我们也可以允许许多函数中的少数函数执行。假设我们想限制除阶乘()函数之外的所有其他数学模块。

示例:

## 蟒蛇 3

```py
# factorial() will be executed
from math import *
exec("print(factorial(5))", {"factorial":factorial})
```

输出:

```py
120
```

我们还可以更改这些预定义方法的名称，并在执行过程中为它们提供用户定义的名称。我们可以将函数的名称从**阶乘()**改为**事实()**，这是用户自定义的。

示例:

## 蟒蛇 3

```py
# factorial() renamed as fact
from math import *
exec('print(fact(5))', {'fact': factorial})
```

输出:

```py
120
```

现在让我们看看在传递全局和局部参数时还能做什么。使用局部参数，我们可以根据需要实现这些功能。

示例:

## 蟒蛇 3

```py
from math import *
exec("print(dir())", {"built" : __builtins__}, {"sum": sum, "iter": iter})
```

输出:

```py
['dir', 'print', 'sum']
```

通过这种方式，只有 sum、iter 方法以及所有内置方法可以在 exec()函数中执行。

我们也可以这样限制 _ _ builtins _ _ 的使用:

## 蟒蛇 3

```py
#__builtins__ has been restricted using None
from math import *
exec("print(dir())", {"__builtins__" : None}, {"sum": sum, "print": print, "dir": dir})
```

输出:

```py
['dir', 'print', 'sum']
```

这里只有 sum、print 和 dir 方法将在 exec()函数中执行，而不是所有的内置方法。
本文由 [**【钦莫伊蕾恩卡】**](https://www.linkedin.com/in/lenkachinmoy/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。