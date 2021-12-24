# 检测 Python 中的脚本退出

> 原文:[https://www.geeksforgeeks.org/detect-script-exit-in-python/](https://www.geeksforgeeks.org/detect-script-exit-in-python/)

Python 是一种脚本语言。这意味着 Python 代码是在 Python 解释器的帮助下逐行执行的。当 python 解释器遇到文件结尾字符时，它无法从脚本中检索任何数据。这个 EOF(文件结束)字符与在 Python 中从文件中读取数据时通知文件结束的 EOF 相同。

要检测脚本退出，我们可以使用 Python 内置的[](https://www.geeksforgeeks.org/python-exit-handlers-atexit/)**库。atexit 模块用于**注册**或**取消注册**处理清理的功能。atexit 注册的函数在解释器终止时被自动调用。**

> *****语法:** atexit.register(fun，*args，* * * kwargs)*
> 
> ***参数:**首先提到函数名，然后传递该函数的任何参数。参数用“，”分隔。*
> 
> ***返回:**这个函数返回被调用的乐趣，因此调用是可以追踪的。***

**以下示例演示了如何使用**退出**来*检测脚本退出*:**

## **蟒蛇 3**

```
import atexit

n = 2
print("Value of n:",n)

atexit.register(print,"Exiting Python Script!")
```

****输出:****

```
Value of n: 2
Exiting Python Script! 
```

**在这个简单的程序中，我们传递了一个 print 函数和一个字符串作为 atexit.register 函数的参数。这将 print 语句注册为将在脚本终止时调用的函数。**

**我们也可以使用 register()方法作为 [**装饰器**](https://www.geeksforgeeks.org/decorators-in-python/) 。**

 **## 蟒 3

```
import atexit 

n = 2
print("Value of n:",n)

# Using register() as a decorator 
@atexit.register 
def goodbye(): 
    print("Exiting Python Script!")
```** 

****输出:****

```
Value of n: 2
Exiting Python Script!
```

**Python 提供了各种可以用来退出 python 脚本的函数，你可以在这里[查看。](https://www.geeksforgeeks.org/python-exit-commands-quit-exit-sys-exit-and-os-_exit/)**