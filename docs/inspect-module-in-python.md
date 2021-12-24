# 用 Python 检查模块

> 原文:[https://www.geeksforgeeks.org/inspect-module-in-python/](https://www.geeksforgeeks.org/inspect-module-in-python/)

*检查*模块有助于检查我们编写的代码中存在的对象。由于 Python 是一种面向对象语言，所有编写的代码基本上都是这些对象之间的交互，因此*检查*模块在检查某些模块或某些对象时变得非常有用。我们还可以使用它来获得对某些函数调用或回溯的详细分析，以便调试变得更容易。

*inspect* 模块提供了很多方法，这些方法可以分为两类，即验证令牌类型的方法和检索令牌来源的方法。这两个类别中最常用的方法如下。

### 验证令牌类型的方法:

*   **isclass():** 如果对象是类，则 *isclass()* 方法返回真，否则返回假。当它与 *getmembers()* 函数结合时，它显示类及其类型。它用于检查直播课。

**示例:**

## 蟒蛇 3

```
# import required modules
import inspect

# create class
class A(object):
    pass

# use isclass()
print(inspect.isclass(A))
```

**输出:**

```
True
```

*   **ismodule():** 如果给定的参数是导入的模块，则返回 *true* 。

**示例:**

## 蟒蛇 3

```
# import required modules
import inspect
import numpy

# use ismodule()
print(inspect.ismodule(numpy))
```

**输出:**

```
True
```

*   **isfunction():** 如果给定的参数是一个内置的函数名，这个方法返回 *true* 。

**示例:**

## 蟒蛇 3

```
# import required modules
import inspect

# explicit function
def fun(a):
    return 2*a

# use isfunction()
print(inspect.isfunction(fun))
```

**输出:**

```
True
```

*   **ismethod():** 此方法用于检查传递的参数是否是方法的名称。

**示例:**

## 蟒蛇 3

```
# import required modules
import inspect
import collections

# use ismethod()
print(inspect.ismethod(collections.Counter))
```

**输出:**

```
False
```

### 检索令牌源的方法:

*   **getclass tree()**:*getclass tree()*方法将有助于获取和检查类层次结构。它返回该类及其前面基类的元组。结合返回基类的*getmro()* 方法有助于理解类的层次结构。

**例 1:**

## 蟒蛇 3

```
# import required module
import inspect

# create classes
class A(object):
    pass

class B(A):
    pass

class C(B):
    pass

# not nested
print(inspect.getmro(C))  
```

**输出:**

> (<class>、<class>、<class>、<class>)</class></class></class></class>

**例 2:**

## 蟒蛇 3

```
# import required module
import inspect

# create classes
class A(object):
    pass

class B(A):
    pass

class C(B):
    pass

# nested list of tuples
for i in (inspect.getclasstree(inspect.getmro(C))):
    print(i)
```

**输出:**

> (<class>、())[( <class>、(<class>、))、[( <class>、(<class>、))、[( <class>、(<class>、))]]</class></class></class></class></class></class></class>

*   **getmembers():** 此方法返回作为此方法的参数传递的模块中存在的成员函数。

**示例:**

## 蟒蛇 3

```
# import required module
import inspect
import math

# shows the member functions
# of any module or object
print(inspect.getmembers(math))
```

**输出:**

> [(“_ _ doc _”，“此模块提供对 C 标准定义的数学函数的访问。”)，(' __loader__ '，<class>)，(' __name__ '，' math ')，(' __package__ '，"，(' __spec__ '，ModuleSpec(name='math '，loader= <class>，origin= '内置')，(' acos '，<built-in function="" acos="">)，(' acosh '，<built-in function="" acosh="">)，(' asin '，<built-in function="" asin="">)，(' asinh '，<built-in function="" asinh="">)，(' atan '，<built-in function="" atan="">)，(' <built-in function="" fsum="">)，(' gamma '，<built-in function="" gamma="">)，(' gcd '，<built-in function="" gcd="">)，(' hypot '，<built-in function="" hypot="">)，(' inf '，inf)，(' isclose '，<built-in function="" isclose="">)，(' isfinite '，<built-in function="" isfinite="">)，(' isinf '，<built-in function="" isinf="">)，(' isnan '，<built-in function="" isnan="">)，(' ldexp '，<built-in function="" ldexp="">)，(' lgamma '，<built-in function="" lgamma="">)，(' t '</built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></built-in></class></class>

*   **signature():***signature()*方法帮助用户理解要传递给函数的属性。

## 蟒蛇 3

```
# import required modules
import inspect
import collections

# use signature()
print(inspect.signature(collections.Counter))
```

**输出:**

```
(*args, **kwds)
```

*   **stack():** 此方法有助于检查解释器堆栈或函数的调用顺序。

## 蟒蛇 3

```
# import required module
import inspect

# define explicit function
def Fibonacci(n):
    if n < 0:
        return 0

    elif n == 0:
        return 0

    elif n == 1:
        return 1
    else:
        return Fibonacci(n-1)+Fibonacci(n-2)

# Driver Program
(Fibonacci(12))

# inpsecting interpreter stack
print(inspect.stack())
```

**输出:**

```
[FrameInfo(frame=<frame at 0x000002AC9BF9FD18, file ‘<ipython-input-8-3080f52ca090>’, line 22, code <module>>, filename='<ipython-input-8-3080f52ca090>’, lineno=22, function='<module>’, code_context=[‘print(inspect.stack())\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BAABA38, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, line 3331, code run_code>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, lineno=3331, function=’run_code’, code_context=[‘                    exec(code_obj, self.user_global_ns, self.user_ns)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9A94B608, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, line 3254, code run_ast_nodes>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, lineno=3254, function=’run_ast_nodes’, code_context=[‘                    if (await self.run_code(code, result,  async_=asy)):\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BA8D768, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, line 3063, code run_cell_async>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, lineno=3063, function=’run_cell_async’, code_context=[‘                       interactivity=interactivity, compiler=compiler, result=result)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C452618, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\async_helpers.py’, line 68, code _pseudo_sync_runner>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\async_helpers.py’, lineno=68, function=’_pseudo_sync_runner’, code_context=[‘        coro.send(None)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BEE1778, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, line 2886, code _run_cell>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, lineno=2886, function=’_run_cell’, code_context=[‘            return runner(coro)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BE85FC8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, line 2858, code run_cell>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\IPython\\core\\interactiveshell.py’, lineno=2858, function=’run_cell’, code_context=[‘                raw_cell, store_history, silent, shell_futures)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C464208, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\zmqshell.py’, line 536, code run_cell>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\zmqshell.py’, lineno=536, function=’run_cell’, code_context=[‘        return super(ZMQInteractiveShell, self).run_cell(*args, **kwargs)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BECB108, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\ipkernel.py’, line 300, code do_execute>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\ipkernel.py’, lineno=300, function=’do_execute’, code_context=[‘                res = shell.run_cell(code, store_history=store_history, silent=silent)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BF9FAF8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, line 209, code wrapper>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, lineno=209, function=’wrapper’, code_context=[‘                    yielded = next(result)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BECAEB8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelbase.py’, line 541, code execute_request>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelbase.py’, lineno=541, function=’execute_request’, code_context=[‘                user_expressions, allow_stdin,\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BF9F6B8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, line 209, code wrapper>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, lineno=209, function=’wrapper’, code_context=[‘                    yielded = next(result)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BEE1BD8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelbase.py’, line 268, code dispatch_shell>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelbase.py’, lineno=268, function=’dispatch_shell’, code_context=[‘                yield gen.maybe_future(handler(stream, idents, msg))\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BFA0378, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, line 209, code wrapper>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, lineno=209, function=’wrapper’, code_context=[‘                    yielded = next(result)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C44A848, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelbase.py’, line 361, code process_one>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelbase.py’, lineno=361, function=’process_one’, code_context=[‘        yield gen.maybe_future(dispatch(*args))\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BE85368, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, line 748, code run>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, lineno=748, function=’run’, code_context=[‘                        yielded = self.gen.send(value)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C456048, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, line 787, code inner>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\gen.py’, lineno=787, function=’inner’, code_context=[‘                self.run()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BE882D8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\ioloop.py’, line 743, code _run_callback>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\ioloop.py’, lineno=743, function=’_run_callback’, code_context=[‘            ret = callback()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C4519A8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\ioloop.py’, line 690, code <lambda>>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\ioloop.py’, lineno=690, function='<lambda>’, code_context=[‘                lambda f: self._run_callback(functools.partial(callback, future))\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BEE5808, file ‘D:\\Software\\Anaconda\\lib\\asyncio\\events.py’, line 88, code _run>, filename=’D:\\Software\\Anaconda\\lib\\asyncio\\events.py’, lineno=88, function=’_run’, code_context=[‘            self._context.run(self._callback, *self._args)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9BEC9798, file ‘D:\\Software\\Anaconda\\lib\\asyncio\\base_events.py’, line 1782, code _run_once>, filename=’D:\\Software\\Anaconda\\lib\\asyncio\\base_events.py’, lineno=1782, function=’_run_once’, code_context=[‘                handle._run()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C44BB88, file ‘D:\\Software\\Anaconda\\lib\\asyncio\\base_events.py’, line 538, code run_forever>, filename=’D:\\Software\\Anaconda\\lib\\asyncio\\base_events.py’, lineno=538, function=’run_forever’, code_context=[‘                self._run_once()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C44B9A8, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\platform\\asyncio.py’, line 153, code start>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\tornado\\platform\\asyncio.py’, lineno=153, function=’start’, code_context=[‘            self.asyncio_loop.run_forever()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9C335248, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelapp.py’, line 583, code start>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel\\kernelapp.py’, lineno=583, function=’start’, code_context=[‘            self.io_loop.start()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC9A980F38, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\traitlets\\config\\application.py’, line 664, code launch_instance>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\traitlets\\config\\application.py’, lineno=664, function=’launch_instance’, code_context=[‘        app.start()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC98403228, file ‘D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel_launcher.py’, line 16, code <module>>, filename=’D:\\Software\\Anaconda\\lib\\site-packages\\ipykernel_launcher.py’, lineno=16, function='<module>’, code_context=[‘    app.launch_new_instance()\n’], index=0), FrameInfo(frame=<frame at 0x000002AC985AE468, file ‘D:\\Software\\Anaconda\\lib\\runpy.py’, line 85, code _run_code>, filename=’D:\\Software\\Anaconda\\lib\\runpy.py’, lineno=85, function=’_run_code’, code_context=[‘    exec(code, run_globals)\n’], index=0), FrameInfo(frame=<frame at 0x000002AC97CE5038, file ‘D:\\Software\\Anaconda\\lib\\runpy.py’, line 193, code _run_module_as_main>, filename=’D:\\Software\\Anaconda\\lib\\runpy.py’, lineno=193, function=’_run_module_as_main’, code_context=[‘                     “__main__”, mod_spec)\n’], index=0)]
```

*   **getsource():** 此方法返回作为 *getsource()* 方法的参数传递的模块、类、方法或函数的源代码。

**示例:**

## 蟒蛇 3

```
# import required modules
import inspect

def fun(a,b):
    # product of 
    # two numbers
    return a*b

# use getsource()
print(inspect.getsource(fun))
```

**输出:**

```
def fun(a,b):
    # product of 
    # two numbers
    return a*b
```

*   **getmodule():** 这个方法返回一个特定对象传递的模块名作为这个方法中的一个参数。

## 蟒蛇 3

```
# import required modules
import inspect
import collections

# use getmodule()
print(inspect.getmodule(collections))
```

**输出:**

*   **getdoc():***getdoc()***方法将该方法中参数的文档作为字符串返回。**

****示例:****

## **蟒蛇 3**

```
# import required modules
import inspect
from tkinter import *

# create object
root = Tk()

# use getdoc()
print(inspect.getdoc(root))
```

****输出:****

> **Tk 的顶层小部件，主要代表应用程序的主窗口
> 。它有一个相关的 Tcl 解释器。**