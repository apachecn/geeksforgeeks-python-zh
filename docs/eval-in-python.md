# Python 中的 eval

> 原文:[https://www.geeksforgeeks.org/eval-in-python/](https://www.geeksforgeeks.org/eval-in-python/)

**python eval()函数**解析表达式参数并将其评估为 Python 表达式，并在程序内运行 Python 表达式(代码)。

### Python eval()语法

> eval(表达式，全局=无，局部=无)

### **Python eval()参数**

*   **表达式:**该字符串作为 Python 表达式进行解析和计算
*   **全局(可选):**指定可用全局方法和变量的字典。
*   **局部变量(可选):**指定可用局部方法和变量的另一个字典。

## Python eval()示例

### 示例 1:演示 eval()使用的示例

让我们借助一个简单的 Python 程序来探索它。 **function_creator** 是对用户创建的数学函数进行求值的函数。

## 蟒蛇 3

```
from math import *

def secret_function():
    return "Secret key is 1234"

def function_creator():

    # expression to be evaluated
    expr = input("Enter the function(in terms of x):")

    # variable used in expression
    x = int(input("Enter the value of x:"))

    # evaluating expression
    y = eval(expr)

    # printing evaluated result
    print("y = {}".format(y))

if __name__ == "__main__":
    function_creator()
```

**输出:**

```
Enter the function(in terms of x):x*(x+1)*(x+2)
Enter the value of x:3
y = 60
```

**让我们稍微分析一下代码:**

*   The above function takes any expression in the variable **x** as input.
*   Then the user must enter a value **x** .
*   Finally, we pass **expr** as a parameter and use **eval ()** built-in function to evaluate python expression.

### 示例 2:使用求值函数的数学运算

## 蟒蛇 3

```
evaluate = 'x*(x+1)*(x+2)'
print(evaluate)
print(type(evaluate))

x = 3
print(type(x))

expression = eval(evaluate)
print(expression)
print(type(expression))
```

**Output**

```
x*(x+1)*(x+2)
<class 'str'>
<class 'int'>
60
<class 'int'>

```

## **评估的漏洞问题**

我们当前版本的 **function_creator** 有几个漏洞。用户可以很容易地暴露程序中隐藏的值，或者调用一个危险的函数，因为 eval 会执行传递给它的任何东西。

**比如你这样输入:**

```
Enter the function(in terms of x):secret_function()

Enter the value of x:0
```

**你会得到输出:**

```
y = Secret key is 1234
```

另外，考虑一下在 python 程序中导入 **os** 模块的情况。os 模块提供了使用操作系统功能(如读取或写入文件)的可移植方式。一个命令就可以删除系统中的所有文件。当然，在大多数情况下(比如桌面程序)，用户不能通过编写自己的 python 脚本做更多的事情，但是在某些应用程序中(比如 web 应用程序、kiosk 计算机)，这可能是一个风险！

解决方案是将**评估**限制为我们想要提供的函数和变量。

## **确保评估安全**

**eval** 函数具有显式传递它可以访问的函数或变量列表的功能。我们需要以字典的形式把它作为一个论点传递出去。

## 蟒 3

```
from math import *

def secret_function():
    return "Secret key is 1234"

def function_creator():

    # expression to be evaluated
    expr = input("Enter the function(in terms of x):")

    # variable used in expression
    x = int(input("Enter the value of x:"))

    # passing variable x in safe dictionary
    safe_dict['x'] = x

    # evaluating expression
    y = eval(expr, {"__builtins__": None}, safe_dict)

    # printing evaluated result
    print("y = {}".format(y))

if __name__ == "__main__":

    # list of safe methods
    safe_list = ['acos', 'asin', 'atan', 'atan2', 'ceil', 'cos',
                 'cosh', 'degrees', 'e', 'exp', 'fabs', 'floor',
                 'fmod', 'frexp', 'hypot', 'ldexp', 'log', 'log10',
                 'modf', 'pi', 'pow', 'radians', 'sin', 'sinh', 'sqrt',
                 'tan', 'tanh']

    # creating a dictionary of safe methods
    safe_dict = dict([(k, locals().get(k, None)) for k in safe_list])

    function_creator()
```

**现在如果我们尝试运行上面的程序，比如:**

```
Enter the function(in terms of x):secret_function()
Enter the value of x:0
```

**我们得到输出:**

```
NameError: name 'secret_function' is not defined
```

**让我们一步一步分析上面的代码:**

*   First, we create a list of methods that we want to allow as **safe _ list** .
*   Next, we create a dictionary of security methods. In this dictionary, **key** is the method name, and **value** is their local namespace.

```
safe_dict = dict([(k, locals().get(k, None)) 
for k in safe_list])
```

*   **Locals ()** is a built-in method that returns a dictionary that maps all methods and variables in the local scope to their namespaces.

```
safe_dict['x'] = x
```

在这里，我们也将局部变量 **x** 添加到 safe_dict 中。除了 **x** 之外，没有任何局部变量会被 **eval** 函数识别。

*   **eval** accepts dictionaries of **local** and **global** variables as parameters. Therefore, in order to ensure that there is no built-in method available for **eval** expression, we pass another dictionary with **safe _ dict** as follows:

```
y = eval(expr, {"__builtins__":None}, safe_dict)
```

因此，通过这种方式，我们使我们的 **eval** 功能免受任何可能的黑客攻击！

## **评估的用途**

**eval** 由于安全原因使用不多，正如我们上面探讨的那样。

**尽管如此，它在某些情况下还是派上了用场，比如:**

*   You may want to use it to let users enter their own "script applet": small expressions (or even small functions), which can be used to customize the behavior of complex systems.
*   Eval is sometimes used in applications that need to calculate mathematical expressions. This is much easier than writing an expression parser.

本博客由[尼克尔·库马尔](https://www.facebook.com/nikhilksingh97)投稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。