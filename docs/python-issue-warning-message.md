# Python |发出警告消息

> 原文:[https://www.geeksforgeeks.org/python-issue-warning-message/](https://www.geeksforgeeks.org/python-issue-warning-message/)

**问题–**拥有一个可以发出警告消息的程序(例如，关于不推荐使用的功能或使用问题)。

**代码#1:使用`warnings.warn()`功能**

```py
import warnings

def func(x, y, logfile = None, debug = False):
    if logfile is not None:
        warnings.warn('logfile argument deprecated', 
                                 DeprecationWarning)
```

`warn()`的参数是一个警告消息和一个警告类，它通常是以下之一:用户警告、折旧警告、语法警告、运行时警告、资源警告或未来警告。
警告的处理取决于解释器的执行方式和其他配置。如果运行带有`-W all` 选项的 Python，将获得以下输出:

```py
bash % python3 -W all example.py
example.py:5: DeprecationWarning: logfile argument is deprecated
 warnings.warn('logfile argument is deprecated', DeprecationWarning) 
```

通常，警告只会在标准错误时产生输出消息。要将警告变为异常，请使用`-W error`选项。

**代码#2 :**

```py
bash % python3 -W error example.py

Traceback (most recent call last):
    File "example.py", line 10, in <module>func(2, 3, logfile ='log.txt')
    File "example.py", line 5, in func
        warnings.warn('logfile argument is deprecated', 
                      DeprecationWarning)
DeprecationWarning: logfile argument is deprecated
bash %</module> 
```

发出警告消息通常是维护软件和帮助用户解决问题的一种有用的技术，这些问题不一定会上升到完全异常的程度。

**代码#3:销毁文件而不关闭文件产生的警告消息。**

```py
import warnings

warnings.simplefilter('always')
f = open('/etc/passwd')

del f
```

**输出:**

```py
__main__:1: ResourceWarning: unclosed file 
<_io.TextIOWrapper name='/etc/passwd' mode='r' encoding='UTF-8'> 
```

*   默认情况下，不会显示所有警告消息。Python 的 **-W** 选项可以控制警告消息的输出。
*   -W all 将输出所有警告消息，-W ignore 忽略所有警告，-W error 将警告变为异常。
*   或者，可以使用 **warnings.simplefilter()** 功能来控制输出。的参数始终会显示所有警告消息，忽略会忽略所有警告，错误会将警告转化为异常。
*   警告模块提供了多种与过滤和处理警告消息相关的高级配置选项。