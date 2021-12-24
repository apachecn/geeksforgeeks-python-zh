# Python |基础程序崩溃调试

> 原文:[https://www . geesforgeks . org/python-basic-程序-崩溃-调试/](https://www.geeksforgeeks.org/python-basic-program-crash-debugging/)

如果程序因异常而崩溃，以 **python3 -i** 的形式运行程序对于简单地四处查看来说是一个有用的工具。一旦程序终止， **-i** 选项就会启动交互式外壳。从那里，可以探索环境。

**代码#1:给定代码**

```py
# abc.py
def func(n):
    return n + 10

func('Hello')
```

**代码#2:运行 python3 -i 产生如下**

```py
bash % python3 -i sample.py
Traceback (most recent call last):
    File "sample.py", line 6, in <module>
        func('Hello')
    File "sample.py", line 4, in func
        return n + 10
TypeError: Can't convert 'int' object to str implicitly
```

```py
func(10)
```

**输出:**

```py
20
```

下一步是崩溃后启动 python 调试器，如下代码所示。

**代码#3 :**

```py
import pdb
pdb.pm()
```

**输出:**

```py
> sample.py(4)func()
-> return n + 10
(Pdb) w
  sample.py(6)()
-> func('Hello')
> sample.py(4)func()
-> return n + 10
(Pdb) print n
'Hello'
(Pdb) q
```

如果代码被深埋在一个很难获得交互外壳的环境中(例如在服务器中)，捕捉错误并产生回溯，如下代码所示。

**代码#4:**

```py
import traceback
import sys

try:
    func(arg)
except:
    print('**** AN ERROR OCCURRED ****')
    traceback.print_exc(file = sys.stderr)
```

如果程序没有崩溃，但它产生了错误的答案或工作错误，那么仅仅在感兴趣的地方注入几个`print()`调用通常没有问题。然而，有一些相关的技术令人感兴趣。首先，`traceback.print_stack()`函数将立即在该点创建程序的堆栈跟踪，如下代码所示。

**代码#5 :**

```py
def sample(n):
    if n > 0:
        sample(n-1)
    else:
        traceback.print_stack(file = sys.stderr)

sample(5)
```

**输出:**

```py
File "", line 1, in <module>
File "", line 3, in sample
File "", line 3, in sample
File "", line 3, in sample
File "", line 3, in sample
File "", line 3, in sample
File "", line 5, in sample
```

或者，也可以使用`pdb.set_trace()`作为–

**代码#6:**

```py
import pdb
def func(arg):
    ...
    pdb.set_trace()
    ...
```

手动启动调试器

这可能是一种有用的技术，用于探查大型程序的内部，并回答关于控制流或函数参数的问题。