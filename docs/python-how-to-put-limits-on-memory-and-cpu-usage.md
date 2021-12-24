# Python |如何限制内存和 CPU 的使用

> 原文:[https://www . geesforgeks . org/python-如何限制内存和 cpu 的使用/](https://www.geeksforgeeks.org/python-how-to-put-limits-on-memory-and-cpu-usage/)

本文旨在展示如何限制正在运行的程序的内存或 CPU 使用。要做到这一点，可以使用**资源模块**，这样两个任务都可以很好地执行，如下面给出的代码所示:

**代码#1:限制 CPU 时间**

```py
# importing libraries
import signal
import resource
import os

# checking time limit exceed
def time_exceeded(signo, frame):
    print("Time's up !")
    raise SystemExit(1)

def set_max_runtime(seconds):
    # setting up the resource limit
    soft, hard = resource.getrlimit(resource.RLIMIT_CPU)
    resource.setrlimit(resource.RLIMIT_CPU, (seconds, hard))
    signal.signal(signal.SIGXCPU, time_exceeded)

# max run time of 15 millisecond
if __name__ == '__main__':
    set_max_runtime(15)
    while True:
        pass
```

当运行该代码的时间到期，程序可以清理并退出时，就会产生 SIGXCPU 信号。

**代码#2:为了限制内存使用，代码对总地址空间**进行了限制

```py
# using resource 
import resource

def limit_memory(maxsize):
    soft, hard = resource.getrlimit(resource.RLIMIT_AS)
    resource.setrlimit(resource.RLIMIT_AS, (maxsize, hard))
```

当没有更多的内存可用时，程序将开始生成内存错误和内存限制异常。

**它是如何工作的？**

*   要设置特定资源的软限制和硬限制，请使用 **setrlimit()** 函数。
*   软限制是操作系统将通过信号通知进程或通常限制进程的一个值。
*   值的上限由硬限制定义，它可用于软限制。
*   虽然硬限制可以降低，但用户进程永远不能提高它，它由系统管理员设置的系统范围参数控制。(即使过程降低了自身)。
*   **setrlimit()** 功能还可以用来设置子进程数量、打开文件数量和类似系统资源的限制。

本文中的代码仅适用于 Unix 系统，可能不适用于所有这些系统。