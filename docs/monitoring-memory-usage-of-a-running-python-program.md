# 监控正在运行的 Python 程序的内存使用情况

> 原文:[https://www . geesforgeks . org/monitoring-memory-usage-of-a-running-python-program/](https://www.geeksforgeeks.org/monitoring-memory-usage-of-a-running-python-program/)

管理内存在任何编程逻辑中都很重要，但这对于 python 来说是必要的。因为 python 用在 Ml 和 AI 中，使用大量需要管理的数据。内存泄漏，即程序运行几个小时后内存不足。为了管理这些内存泄漏，内存监控是必不可少的。监控内存也称为分析。作为一名开发人员，我们必须对我们的程序进行概要分析，并尽可能少地使用内存分配。

**方法 1:使用 Tracemalloc**

Tracemalloc 是一个库模块，跟踪 python 中的每个内存块。在运行时使用 start()开始跟踪。该库模块还可以提供有关已分配内存块的总大小、数量和平均大小的信息。让我们用一个恰当的例子来说明它的功能

## 蟒蛇 3

```
# importing the module
import tracemalloc

# code or function for which memory
# has to be monitored
def app():
    lt = []
    for i in range(0, 100000):
        lt.append(i)

# starting the monitoring
tracemalloc.start()

# function call
app()

# displaying the memory
print(tracemalloc.get_traced_memory())

# stopping the library
tracemalloc.stop()
```

**输出:**

输出以(当前，峰值)形式给出，即当前内存是代码当前使用的内存，峰值内存是程序执行时使用的最大空间。

```
(0,3617252)
```

**方法二:使用 Psutil**

Psutil 是一个 python 系统库，用于跟踪系统中的各种资源及其利用率。该库用于分析、限制和管理流程资源。要安装它，请执行以下操作-

```
sudo pip install psutil [Linux]
pip install psutill [Windows]
```

让我们用一个例子来看看这个。您所要做的就是在代码中添加装饰函数和 process_memory 函数，这将为您提供代码所消耗的内存以及它的前后值。

## 蟒蛇 3

```
# importing libraries
import os
import psutil

# inner psutil function
def process_memory():
    process = psutil.Process(os.getpid())
    mem_info = process.memory_info()
    return mem_info.rss

# decorator function
def profile(func):
    def wrapper(*args, **kwargs):

        mem_before = process_memory()
        result = func(*args, **kwargs)
        mem_after = process_memory()
        print("{}:consumed memory: {:,}".format(
            func.__name__,
            mem_before, mem_after, mem_after - mem_before))

        return result
    return wrapper

# instantiation of decorator function
@profile

# main code for which
# memory has to be monitored
def func():
    x = [1] * (10 ** 7)
    y = [2] * (4 * 10 ** 8)
    del x
    return y

func()
```

**输出:**

```
func: consumed memory: 307,261,440
```

**方法 3:使用经典的内存分析器**

来自 PyPI 的内存分析器是一个 python 库模块，用于监控进程内存。它使用 psutil 代码来创建装饰器，然后使用它来获取内存分布。有了这个 pypi 模块，通过导入可以节省行，直接调用装饰器。要安装，请使用以下工具-

```
pip install -U memory_profiler
```

让我们通过一个代码来看看这个-

## 蟒蛇 3

```
# importing the library
from memory_profiler import profile

# instantiating the decorator
@profile
# code for which memory has to
# be monitored
def my_func():
    x = [x for x in range(0, 1000)]
    y = [y*100 for y in range(0, 1500)]
    del x
    return y

if __name__ == '__main__':
    my_func()
```

**输出:**

输出显示代码中每一行消耗的内存。使用内存分析器实现查找内存消耗非常容易，因为我们直接调用装饰器，而不是编写全新的代码。

```
Line #    Mem usage    Increment  Occurences   Line Contents
============================================================
     2     30.5 MiB     30.5 MiB           1   @profile
     3                                         def my_func():
     4     30.6 MiB      0.1 MiB        1003       x = [x for x in range(0,1000)]
     5     30.7 MiB      0.1 MiB        1503       y = [y*100 for y in range(0,1500)]
     6     30.7 MiB      0.0 MiB           1       del x
     7     30.7 MiB      0.0 MiB           1       return y  
```